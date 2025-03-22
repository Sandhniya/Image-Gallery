Activity An Interactive Image Gallery using JavaScript, HTML, and CSS.
Date:22.03.20205
Aim:
To create an interactive image gallery with:

Horizontal scrollable images.

Captions that appear on hover.

Next and Previous buttons for navigation.

Responsive design using HTML, CSS, and JavaScript.

Algorithm:
HTML Structure:
Create a gallery container and individual image containers with captions.

Add Next and Previous buttons for navigation.

CSS Styling:
Use flexbox to arrange images horizontally.

Add hover effects for captions.

Position buttons on the sides for navigation.

JavaScript:
Track the current image index.

Move gallery left or right on button click.

Ensure smooth transitions and looping (First to Last/Last to First).

Footer:
Display learner's name and register number at the bottom.
PROGRAM:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IMAGE Gallery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background-color: #000000;
            display: flex;
            flex-direction: column;
            height: 100vh;
        }

        .gallery-container {
            position: relative;
            overflow: hidden;
            width: 80%;
            height:fit-content;
            margin: 40px auto;
            max-width: 800px;
            background-color: #ddd;
            border-radius: 10px;
        }

        .image-wrapper {
            display: flex;
            transition: transform 1s ease-in-out;
        }

        .gallery-image {
            min-width: 100%;
            position:static;
        }

        .gallery-image img {
            width: 110%;
            border-radius: 20px;
            height: 65%;
            object-fit: cover;
        }

        .caption {
            position: absolute;
            bottom: 10px;
            left: 10px;
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            padding: 5px 10px;
            border-radius: 15px;
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }

        .gallery-image:hover .caption {
            opacity: 1;
        }

        .nav-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            border: none;
            color: rgb(255, 255, 255);
            padding: 10px;
            cursor: pointer;
            border-radius: 60%;
        }

        .prev-btn {
            left: 10px;
        }

        .next-btn {
            right: 10px;
        }

        .footer {
            text-align: center;
            padding: 10px;
            background-color: #333;
            color: white;
            margin-top: auto;
        }

        @media (max-width: 768px) {
            .gallery-container {
                height: 200px;
            }
        }
    </style>
</head>
<body>

    <div class="gallery-container">
        <div class="image-wrapper" id="imageWrapper">
            <div class="gallery-image">
                <img src="C:\Users\admin\OneDrive\Pictures\New folder\Stranger_Things_logo.png" alt="Image 1">
                <div class="caption">STRANGER THINGS</div>
            </div>
            <div class="gallery-image">
                <img src="C:\Users\admin\OneDrive\Pictures\New folder\1 IMAGE.jpg" alt="Image 2">
                <div class="caption">STRANGER THINGS</div>
            </div>
            <div class="gallery-image">
                <img src="C:\Users\admin\OneDrive\Pictures\New folder\Stranger-Things-1.webp" alt="Image 3">
                <div class="caption">STRANGER THINGS</div>
            </div>
        </div>
        <button class="nav-btn prev-btn" onclick="prevImage()">&#10094;</button>
        <button class="nav-btn next-btn" onclick="nextImage()">&#10095;</button>
    </div>

    <div class="footer">
        SANDHIYA SREE B (212223220093)
    </div>

    <script>
        let currentIndex = 0;

        function updateGallery() {
            const imageWrapper = document.getElementById('imageWrapper');
            const totalImages = document.querySelectorAll('.gallery-image').length;
            imageWrapper.style.transform = `translateX(-${currentIndex * 100}%)`;

            if (currentIndex >= totalImages) {
                currentIndex = 0;
            } else if (currentIndex < 0) {
                currentIndex = totalImages - 1;
            }
        }

        function nextImage() {
            currentIndex++;
            updateGallery();
        }

        function prevImage() {
            currentIndex--;
            updateGallery();
        }
    </script>

</body>
</html>
```
OUTPUT:
![image](https://github.com/user-attachments/assets/f914b8bf-88d4-4558-8707-80feb0eeb6e6)

![image](https://github.com/user-attachments/assets/2c563fb4-1c50-4c3a-859b-fa43d40889d2)

![image](https://github.com/user-attachments/assets/edc21723-9fd9-439c-91bc-358282368523)



