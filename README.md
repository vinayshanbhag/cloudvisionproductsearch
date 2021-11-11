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

             Magic Mouse       1.00      1.00      1.00         1
              Galaxy S20       0.00      0.00      0.00         1
               Nest Mini       0.50      1.00      0.67         1
              Roku Ultra       1.00      1.00      1.00         1
                 Deco M9       1.00      0.67      0.80         3
               Airpods 2       1.00      1.00      1.00         2
          Magic Keyboard       1.00      1.00      1.00         1
               iPhone 13       0.00      0.00      0.00         1
         Nest Thermostat       0.50      1.00      0.67         1
              Echo Dot 3       0.75      1.00      0.86         3
           Mac Mini 2020       1.00      1.00      1.00         3
   Nest Doorbell Battery       0.50      1.00      0.67         1
      Galaxy S21 Plus 5G       0.00      0.00      0.00         1
               iPhone 6S       0.00      0.00      0.00         1
    Apple Watch Series 6       1.00      0.33      0.50         3
    Apple Watch Series 4       0.60      1.00      0.75         3
     Macbook Pro 13 2020       1.00      0.50      0.67         2
          Macbook Pro 16       1.00      1.00      1.00         1
              Galaxy S10       0.00      0.00      0.00         1
    Apple Watch Series 3       0.00      0.00      0.00         3
        Nest Cam Outdoor       1.00      1.00      1.00         1
           iPhone 13 Pro       1.00      1.00      1.00         1
Nest Learning Thermostat       0.50      1.00      0.67         1
     Nest Doorbell Wired       0.00      0.00      0.00         1
              Echo Dot 4       1.00      0.33      0.50         3
    Apple Watch Series 5       0.50      1.00      0.67         3
                  Echo 2       1.00      1.00      1.00         3
     Nest Cam Floodlight       1.00      1.00      1.00         1
         Nest Cam Indoor       0.50      1.00      0.67         1

               micro avg       0.76      0.69      0.72        49
               macro avg       0.63      0.68      0.62        49
            weighted avg       0.69      0.69      0.65        49
```
![cm](https://user-images.githubusercontent.com/5519039/141360938-487dff3a-e4a3-4382-894b-de8eaa4657d1.png)

