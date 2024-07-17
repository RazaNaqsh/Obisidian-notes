
scraping meanings grabbing data over the internet from sites , and what it allows us to ethically

Some sites like Hackernews allows us to scrape the news data
## Tools to scrape

We use tools like 
- BeautifulSoup4: pip3 install beautifulsoup4 (allows us to use the html and grab different data)
- requests: pip3 install requests (allows us to download initially that html)


### how to do it

```
import requests

from bs4 import BeautifulSoup


res = requests.get("https://news.ycombinator.com/news")

# print(res.text)
```
the res gives us the status
and .text method give us all the html content

Now we will use beautiful soup to cleanup the data
what it does is it converts the string into actual objects that we can use and manipulate


```
res = requests.get("https://news.ycombinator.com/news")

# print(res.text)

soup = BeautifulSoup(res.text, "html.parser")

  

print(soup.body.contents)
print(soup.find_all("div"))
print(soup.find("a"))  # finds the first item
print(soup.select('.score')) #selects with the css selectors
```

soup object gives us the content we want


```
import requests

from bs4 import BeautifulSoup


res = requests.get("https://news.ycombinator.com/news")

# print(res.text)

soup = BeautifulSoup(res.text, "html.parser")


links = soup.select(".titleline a") #gets the a tag inside of the span tag 

votes = soup.select(".score")

  

def create_custom_hn(links, votes):

    hn = []

    for idx, item in enumerate(links):

        title = links[idx].getText()     #Gets the title of the link

        href = links[idx].get("href", None)  #gets the link of the title

        hn.append({"title": title, "link": href}) #organizing into a dictionary

    return hn

  
  

print(create_custom_hn(links, votes))
```



welp scraping is all about figuring and assuming how to sort the data in the way you want


```
import requests

from bs4 import BeautifulSoup

import pprint

  

res = requests.get("https://news.ycombinator.com/news")

res2 = requests.get("https://news.ycombinator.com/news?p=2")

soup = BeautifulSoup(res.text, "html.parser")

soup2 = BeautifulSoup(res2.text, "html.parser")

  

links = soup.select(".titleline > a")  
subtext = soup.select(".subtext")

links2 = soup2.select(".titleline > a")  
subtext2 = soup2.select(".subtext")

  

mega_links = links + links2

mega_subtext = subtext + subtext2

  
  

def sort_stories_by_votes(hnlist):

    return sorted(hnlist, key=lambda k: k["votes"], reverse=True)

  
  

def create_custom_hn(links, subtext):

    hn = []

    for idx, item in enumerate(links):

        title = item.getText()

        href = item.get("href", None)

        vote = subtext[idx].select(".score")

        if len(vote):

            points = int(vote[0].getText().replace(" points", ""))

            if points > 99:

                hn.append({"title": title, "link": href, "votes": points})

    return sort_stories_by_votes(hn)

  
  

pprint.pprint(create_custom_hn(mega_links, mega_subtext))
```