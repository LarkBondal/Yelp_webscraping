import scrapy
from bs4 import BeautifulSoup


class YelpScraperSpider(scrapy.Spider):
    name = 'Yelpscraper'
    start_url = ['https://www.yelp.com/search?find_desc=Local+Favorite+Restaurants&find_loc=Las+Vegas%2C+NV&attrs=NewBusiness'
    ]


    def parse(self, response):
        restaurant_names = response.css('.businessName__09f24__EYSZE').extract()
        restaurant_reviews = response.css('.css-8xcil9').extract()
        restaurant_age = response.css('.display--inline-block__09f24__fEDiJ margin-t0-5__09f24__gboxT border-color--default__09f24__NPAKY').extract()


        for item in zip(restaurant_names, restaurant_reviews, restaurant_age):
            all_items = {
                'restaurant_name' : BeautifulSoup(item[0]).text,
                'restaurant_reviews' : BeautifulSoup(item[1]).text,
                'restaurant_age' : BeautifulSoup(item[2]).text
            }


            yield all_items
