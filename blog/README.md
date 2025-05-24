# How to Add a New Blog Post

This document outlines the steps to add a new blog post to this website. The process has been simplified so you no longer need to manually edit the main `blog/index.html` page to list your new post.

## Steps

1.  **Create Your Blog Post HTML File:**
    *   Write your blog post content directly in an HTML file.
    *   Save this file in the `blog/` directory (the same directory where this `README.md` is located). For example, `mi-nuevo-articulo.html`.

2.  **Add Metadata to Your HTML File:**
    *   Inside the `<head>` section of your new HTML file, you need to add a special `<script>` tag that contains metadata about your post. This metadata is used to generate the post listing on the main blog page (`blog/index.html`).
    *   The script tag must have `type="application/json"` and `id="blog-metadata"`.
    *   The content of the script tag should be a JSON object with the following properties:
        *   `title`: (String) The title of your blog post.
        *   `date`: (String) The publication date (e.g., "25 de Diciembre de 2024").
        *   `excerpt`: (String) A short summary or teaser of your post.
        *   `image`: (String) The URL of the main image for your post. You can use a placeholder service like `https://placehold.co/` or upload an image to your repository and link to it.
        *   `filename`: (String) The exact filename of your HTML blog post (e.g., `mi-nuevo-articulo.html`).

    *   **Example Metadata:**
        ```html
        <head>
            <meta charset="UTF-8">
            <title>Título de Mi Nuevo Artículo</title>
            <!-- Other meta tags as needed -->

            <script type="application/json" id="blog-metadata">
            {
              "title": "Título de Mi Nuevo Artículo",
              "date": "25 de Diciembre de 2024",
              "excerpt": "Este es un resumen breve y atractivo de mi nuevo artículo.",
              "image": "https://placehold.co/800x400/007bff/FFFFFF?text=Nuevo+Artículo&font=roboto",
              "filename": "mi-nuevo-articulo.html"
            }
            </script>

            <!-- Any other styles or scripts specific to this post -->
        </head>
        <body>
            <h1>Título de Mi Nuevo Artículo</h1>
            <p>Contenido completo de tu artículo aquí...</p>
            <!-- Rest of your post -->
        </body>
        </html>
        ```

3.  **Add Filename to `posts.js`:**
    *   Open the file `blog/posts.js`.
    *   This file contains a JavaScript array called `blogPosts`.
    *   Add the filename of your new HTML post (e.g., `"mi-nuevo-articulo.html"`) as a new string to this array.
    *   **Example `posts.js` update:**
        If `posts.js` was:
        ```javascript
        const blogPosts = [
          "cuidado-medico-en-casa.html",
          "dummy-post.html"
        ];
        ```
        And you added `mi-nuevo-articulo.html`, it should become:
        ```javascript
        const blogPosts = [
          "cuidado-medico-en-casa.html",
          "dummy-post.html",
          "mi-nuevo-articulo.html"
        ];
        ```

4.  **Commit and Push Your Changes:**
    *   Once you've created the HTML file and updated `posts.js`, commit these changes to your Git repository and push them. The website should automatically update with your new post.

That's it! Your new blog post should now appear on the blog page.
