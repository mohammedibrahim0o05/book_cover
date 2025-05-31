# Ex.06 Book Front Cover Page Design
# Name Mohammed Ibrahim MN
# Date 19/04/25
# AIM:
To design a book front cover page using HTML and CSS.

# DESIGN STEPS:
## Step 1:
Create a Django Admin project.

## Step 2:
Create an app in the Django interface.

## Step 3:
Create a folder named 'static' in the app folder.

## Step 4:
Create a new HTML file in the static folder.

## Step 5:
Write the HTML code with relevant CSS properties.

## Step 6:
Choose the appropriate style and color scheme.

## Step 7:
Insert the images in their appropriate places.

## Step 8:
Publish the website in the LocalHost.

# PROGRAM:
## Settings.py 
```python
import os 
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'mybookcover'
]
```
## Views.py 
```python
from django.shortcuts import render
def bookCover (request) :
    host = request.get_host()
    port = host.split(':')[1] 
    print(f'The server is running on the port {port}')
    
    # Log the GET request
    print('GET request received...')
    
    # Render the HTML page
    response = render(request, 'mybookcover/bookcover.html') 
    
    # Log the status code
    print(f'Status code {response.status_code}')
    print('HTML response sent successfully.')
    return response

```
## Urls.py 
```python
from django.urls import path
from .views import bookCover
# from .views import
urlpatterns = [
    path('', bookCover, name='cover'),
]
```
## Project Urls.py 
```python
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',include('mybookcover.urls'))
]
```
## Bookcover.html 
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Power of Positive Thinking</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sora:wght@100..800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0px;
            padding: 0px;
        }

        .book-cover {
            background: url(https://i.pinimg.com/200x/0f/6c/dd/0f6cdd636bde06a9098c21df6768161a.jpg)no-repeat center/cover;
            width: 400px;
            height: 600px;
            font-family: "Sora", sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            border: 2px solid black;
            border: 2px solid white;

        }

        .title {
            display: flex;
            width: 80%;
            gap: 10%;
            font-size: 20px;
            display: flex;
            justify-content: center;
            margin-top: 150px;
            /* margin-top: 200px; */
        }

        .head {
            font-family: 'Times New Roman', Times, serif;
        }

        .description {
            font-size: 30px;


        }

        .foot {
            font-weight: 100;
            font-family: 'Times New Roman', Times, serif;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            margin-top: 50px;
        }

        body {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 150px;
            background-color: black;
        }
    </style>
</head>

<body>
    <div class="book-cover">
        <div class="head">
            <p>THE INTERNATIONAL BEST SELLER</p>

        </div>
        <div class="title">
            <h1>I</h1>
            <h1>K</h1>
            <h1>I</h1>
            <h1>G</h1>
            <h1>A</h1>
            <h1>I</h1>
        </div>
        <div class="foot description">
            <p>The Japanese Secret </p>
            <p>To a Long and Happy Life</p>
        </div>
        <div class="foot">
            <p>HECTOR GARCIA AND FRANCESC MIRALLES</p>
            <p>Bestselling authors of <strong>The Book of ICHIGO ICHIE</strong></p>

        </div>

    </div>
</body>

</html>
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/d294dee8-242f-4d64-be40-5cf6d97d31af)

# RESULT:
The program for designing book front cover page using HTML and CSS is completed successfully.
