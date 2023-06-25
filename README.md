# Cultural Importance of Corn
 
## This is a project for the [Lede Program](https://ledeprogram.com/how-to-apply/) at the Columbia Graduate School of Journalism. 

Initially, I wanted to look at Midwest art museums' collections through Open Access API projects to determine if art museums reflected the regional economies of their home states. I was specifically using 'corn' as my main focus in the Midwestern states.

I quickly discovered that not all APIs are created equal (shoutout to the *amazing* Cleveland Museum of Art for being the only one I found with an included 'Tombstone'). Due to a lack of relevant information, I had to alter my project. Instead, I focused only on The National Gallery of Art's collection and grouped their acquisitions by year and theme to uncover acquisition trends for rural and farming landscape artworks. There were still a few inconclusive results, however. Taking a closer look at the collections data revealed that 8% of artworks weren’t tagged with any keywords and at least 10,000 artworks weren’t included in the dataset. And over half (53%) of the artworks that were recorded weren’t assigned a theme, such as 'landscape' or 'still life'.

As the data stands today, my analysis showed that 11% of 2010s acquisitions were landscapes, making it the highest decade for landscape acquisitions by more than 200%. Nearly 30% of all rural or farm landscapes were acquired in 2015, and 58% of all rural/farm acquisitions occurred in 2010 or later.

And I didn't forget about the corn: .02% of The National Gallery's collection is corn art. 🌽

My ideal scenario for this project would be to dive deeper into artists' residences to determine if their local economies played out within their artwork. That would either require additional tagging within The National Gallery's data, or significant research on each artist's name. 

My main data manipulations were done through pandas in a Jupyter Notebook and included separating out the accession number column into an accession_year column and then merging multiple .csv files to utilize that new column. I used `matplotlib` for the annual acquisitions line chart, Datawrapper for the split bar chart, and then an embed code for the Google Trends map.

### 🍄 ⏫ LEVEL UP ⏫ 🍄
This project was great for leveling up my skills. This was the first time I split a column within pandas to create a new column, and then merge on that column. It was also my first time using `matplotlib` so I was really happy to be able to add in the annotation and arrow. 

### Sources
- [National Gallery GitHub](https://github.com/NationalGalleryOfArt/opendata)
- [Agricultural Statistics](https://www.ers.usda.gov/statefacts)
- [2023 Corn Prices, Economists Predictions according to Yahoo! Finance](https://finance.yahoo.com/news/us-corn-crop-withers-worst-162334551.html?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAADa6XgKdlYkvxq57xWxVUlwADWG8ve3EFojunPLicnEzOo7OP5JxdwwvbnbNO19QorGsY9byN6CR1BIjKLo8a9EM-R8G8qrhDTljuYNcBXrL6R_nZbJ7uVBlHEZoUV2AbEdxhMurd7Hz4OF2K3H1TOP6jh7q58X-UOR33UeDLxgr)
- [The National Gallery History](https://www.nga.gov/research/gallery-archives/nga-history-timeline.html)

## If you want to admire the Cleveland Museum of Art's API

Here is the code I used when I was starting my project:

`import requests
cle_url = "https://openaccess-api.clevelandart.org/api/artworks/?q=corn"
cle_response = requests.get(cle_url)
cle_data = cle_response.json()
print(cle_data.keys())
print("__________________________")
print(cle_data.items())

for cle_artworks in cle_data['data']:
    print(cle_artworks['tombstone'])`
