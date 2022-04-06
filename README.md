# Product search using Google Cloud Vision

Google Vision API Product Search allows retailers to create products, each containing reference images that visually describe the product from a set of viewpoints. Retailers can then add these products to product sets. 

When users query the product set with their own images, Vision API Product Search applies machine learning to compare the product in the user's query image with the images in the retailer's product set, and then returns a ranked list of visually and semantically similar results.

Notebooks in this repo:

1. [Create and Manage a product set](https://github.com/vinayshanbhag/cloudvisionproductsearch/blob/main/Google_Cloud_Vision_Create_a_product_set.ipynb)
2. [Evaluate Google Vision API query results](https://github.com/vinayshanbhag/cloudvisionproductsearch/blob/main/Google_Cloud_Vision_Product_Search.ipynb)

Datasets:
1. [Product images to build a Google Vision product set](https://github.com/vinayshanbhag/images)
2. [Test set of images to evaluate Google Vision API results](https://github.com/vinayshanbhag/test_images)

Summary:

```
                                    precision    recall  f1-score   support

                  Amazon Echo 2       1.00      0.67      0.80         3
           Apple Watch Series 3       0.00      0.00      0.00         3
               Google Nest Mini       1.00      1.00      1.00         1
            Apple iPhone 13 Pro       1.00      1.00      1.00         1
   Apple Magic Keyboard Numeric       1.00      1.00      1.00         1
Google Nest Learning Thermostat       1.00      1.00      1.00         1
           Apple Watch Series 6       1.00      0.67      0.80         3
           Apple Watch Series 5       1.00      1.00      1.00         3
                TP-Link Deco M9       1.00      0.67      0.80         3
            Apple Mac Mini 2020       1.00      1.00      1.00         3
   Google Nest Doorbell Battery       1.00      1.00      1.00         1
      Apple MacBook Pro 16 2019       1.00      1.00      1.00         1
                Apple AirPods 2       1.00      0.50      0.67         2
              Amazon Echo Dot 3       1.00      0.67      0.80         3
              Apple Magic Mouse       1.00      1.00      1.00         1
           Apple Watch Series 4       1.00      1.00      1.00         3
     Samsung Galaxy S21 Plus 5G       1.00      1.00      1.00         1
                     Roku Ultra       1.00      1.00      1.00         1
     Google Nest Doorbell Wired       1.00      1.00      1.00         1
              Amazon Echo Dot 4       1.00      0.67      0.80         3
      Apple MacBook Pro 13 2020       0.00      0.00      0.00         2
             Samsung Galaxy S10       0.00      0.00      0.00         1
         Google Nest Cam Indoor       1.00      1.00      1.00         1
                Apple iPhone 6S       0.00      0.00      0.00         1
             Samsung Galaxy S20       1.00      1.00      1.00         1
        Google Nest Cam Outdoor       1.00      1.00      1.00         1
         Google Nest Thermostat       1.00      1.00      1.00         1
                Apple iPhone 13       1.00      1.00      1.00         1
     Google Nest Cam Floodlight       1.00      1.00      1.00         1

                      micro avg       1.00      0.73      0.85        49
                      macro avg       0.86      0.79      0.82        49
                   weighted avg       0.86      0.73      0.78        49

```
![cm](https://user-images.githubusercontent.com/5519039/141360938-487dff3a-e4a3-4382-894b-de8eaa4657d1.png)

