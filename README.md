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
![cm](https://user-images.githubusercontent.com/5519039/162085682-092da645-542f-40bf-ae81-8e0b69ac647b.png)



|                       |Google Vision Product Search                                                                                                                                                                                        |Azure Custom Vision                                                                                                                                                                                                                                          |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<b>Summary</b>                           |Given a user generated image,<br>finds similar images from product set                                                                                                                                                  |Given a user generated image,<br>finds matching classes<br><br>(softmax probability distribution<br>over output classes)                                                                                                                                                   |
|<b>Image requirements</b>             |Max size: <b>20MB</b><br>Format: jpg, png, bmp, gif<br><br># of images per product:<b> 1-3</b>                                                                                                                                              |Max size: <b>6MB (4MB test)</b><br>Format: jpg, png, bmp, gif<br><br># of images per product: <b>5-100</b><br>(recommended to be same across classes)                                                                                                                                   |
|<b>Image specifications</b>           |In general, Packshot product images<br>are required for training<sup>[Ref:[1](https://en.wikipedia.org/wiki/Packshot)]</sup><br><br>Detailed guidelines<sup>[Ref:[2](https://cloud.google.com/vision/product-search/docs/csv-format#creating_your_reference_images)]</sup>                                                   |Any product image - <br>min 256x256 and max 10240x10240 <sup>[Ref:[3](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/limits-and-quotas)]</sup>                                                                                                         |
|<b>Image upload process</b> (Training)|- Upload files to designated Google Storage bucket<br>- Upload CSV with product metadata<br>- Bulk update product sets<br>- Import limit per batch <b>20000</b><br><br><sup>[Ref:[4](https://cloud.google.com/vision/product-search/docs/csv-format)]</sup>|- Create tags<br>- Bulk update images with tags via SDK<br>- Import limit per batch <b>64</b><br><br><sup>[Ref:[5](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/quickstarts/image-classification?tabs=visual-studio&pivots=programming-language-python)]</sup>|
|<b>Training</b>                       |- Automatically initiated.<br><br>- Index is updated within 30min<br>after product set is updated                                                                                                                            |- Must be initiated by user <br><br>- Training cannot start if any class<br>has less than 5 images.<br><br>- Model must be published to prediction endpoint<br>explicitly before it is available via API                                                                         |
|<b>Prediction</b>                     |- Rest API or SDK takes image and returns<br>matches and scores<br><br>- scores are not absolute and not comparable                                                                                                           |- Rest API or SDK takes image and<br>returns matches and probabilities                                                                                                                                                                                          |


