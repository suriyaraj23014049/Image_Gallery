# Ex.08 Design of Interactive Image Gallery
## Date: 14-11-2024

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
# gallery.html
```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main id="gallery">
        <div class="gallery-container">
            <img src="c:\Users\admin\Desktop\maha.jpg" alt="Image 1" >
            <img src="c:\Users\admin\Desktop\beach s.jpg" alt="Image 2">
            <img src="c:\Users\admin\Desktop\nyt s.jpg" alt="Image 3" >
            <img src="c:\Users\admin\Desktop\flowers s.jpg" alt="Image 4" >
            <img src="c:\Users\admin\Downloads\pool s.jpg" alt="Image 5" >
            <img src="c:\Users\admin\Desktop\food.jpg" alt="Image 6" >
            <img src="c:\Users\admin\Desktop\akki.jpg" alt="Image 7" >
            <img src="c:\Users\admin\Desktop\tourist .jpg" alt="Image 8" >
            <!-- Add more images as needed -->
        </div>
    </main>

    <footer>
        <p>&copy; 2024 Your Website</p>
    </footer>
</body>
</html>
```
##  models.py
```
class Image(models.Model):
    title = models.CharField(max_length=100)
    image = models.ImageField(upload_to='images/')

    def __str__(self):
        return self.title
```
## settings.py
```
ALLOWED_HOSTS = ['*']
```
## styles.css
```
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 10px 0;
}

nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
}

nav ul li {
    margin: 0 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

.gallery-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    padding: 20px;
}

.gallery-container img {
    width: 80%;
    height: 1000;
    border-radius: 10px;
}

footer {
    text-align: center;
    padding: 10px 0;
    background-color: #f1f1f1;
    margin-top: 20px;
}

```
## urls.py
```
from .views import gallery_view

urlpatterns = [
    path('', gallery_view, name='gallery'),
]
```
## views.py
```
from .models import Image

def gallery_view(request):
    images = Image.objects.all()
    return render(request, 'gallery/gallery.html', {'images': images})
```
## OUTPUT:
![Screenshot 2024-11-07 114356](https://github.com/user-attachments/assets/55e04dd3-19d2-4d68-89a4-6cb5dce2fa6c)


## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
