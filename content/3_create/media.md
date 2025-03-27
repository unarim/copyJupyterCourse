# Integrating Media Into Your Content
In this section, you will learn how to embed images, videos, presentations, and GIFs into your course. 

## Images
In Jupyter Books, there are few different ways to include images. Here, we will highlight the way that is most optimal for hosting your website with our provided `build` script, located in the '.github/workflows' directory of our course template.

### Using Markdown
The easiest way is to add the images to the static folder of your project. Once you upload the project to your GitHub you essentially are hosting the images through their services.

To add images in your markdown file that are uploaded in you static folder, you can use the relative path:

`![alternative_imagetext](../static/FILENAME.png)` with as many `../` as you need to move up one level in your folder structure.

Example: `![Image of the DiLER project logo](../../static/logo.png)`

Result: 

![Image of the DiLER project logo](../../static/logo.png)

Alternatively, you can include the image link as follows:
`![alternative_imagetext](https://YOURGITHUBNAME.github.io/PROJECTNAME/static/FILENAME.png)`

As you are able to use essentially any image link, you can add images that are hosted through other websites, too!

### Using HTML
If you want more control about the size, orientation and more, you will have to rely on HTML tags. E.g. the following line of code will present the same image as above only downscaled to a width of 200 pixels.

`<img src="https://DiLER-Digitell.github.io/tutorial_jupyter_books/static/logo.png" alt="Image of the DiLER project logo" class="bg-primary mb-1" width="200px">`

which results in: 

<img src="https://DiLER-Digitell.github.io/tutorial_jupyter_books/static/logo.png" alt="Image of the DiLER project logo" class="bg-primary mb-1" width="200px">

<img src="../../static/logo.png" alt="Image of the DiLER project logo" class="bg-primary mb-1" width="200px">

<img src="https://felixkoerber.github.io/jb/_static/logo.png" alt="logo" class="bg-primary mb-1" width="200px"> 

--- 

**The code above is made up of multiple html keywords, that each control a separate parameter of the image you want to control:**

| Keyword | Description | 
| ----- | -----|
|`<img>` | an HTML tag used to display an image on a web page. |
|`src="../../static/logo.png"` | an attribute that specifies the URL or path to the image file you want to display. |
|`alt="Image of the DiLER project logo"` | an attribute that provides alternative text for the image. This text is used by screen readers for visually impaired users, and it is also displayed when the image cannot be loaded for some reason. |
|`class="bg-primary mb-1"` | an attribute that defines the CSS class or classes to apply to the image. In this case, the class bg-primary sets the background color of the image to a primary color, and mb-1 adds a margin-bottom of 1 unit to the image. |
|`width="200px"` | an attribute that sets the width of the image to 200 pixels. This can be adjusted to suit your needs. |

Simply copy-paste the above line of code and adjust it to your need as necessary to embed every kind of image into your notebooks.

**For a more in-depth exploration of the `img` tag checkout the [w3schools html tutorial](https://www.w3schools.com/html/html_images.asp).**


## Videos, Presentations, GIFs, and more: iframes

As you already learned, Jupyter Book enables you to implement `html` into your books. This allows for the integration of almost every type of media, including - but not limited to - Videos, Presentations, GIFs, Maps and Images via `iframes`.

```{note}
`iframes` or *inlineframes* are HTML-elements, that can be used to embed content from different websites.
```

Inlineframes are structured and implemented like this:

`<iframe src="http://www.example.com/" height="100" width="200" name="iframename">Alternative title</iframe>`

Thus, they essentially follow the same structure as the HTML-image integration.

To quickly generate this code for the media of your choice, you can use a tool like the [iframe-generator](https://www.iframe-generator.com/), where you add the media URL, can change various settings and can then generate the iframe code.

Let us go over different types of media embeddings:

___

### Videos

To add videos, you need to add the "embed"-URL of the video. 
This URL is formatted like this:
`http://www.youtube.com/embed/VIDEO_ID`

Thus, `https://www.youtube.com/watch?v=c-bemNZ-IqA` would become `https://www.youtube.com/embed/c-bemNZ-IqA`.

Added in iframes, it looks like this:

```<iframe src="https://www.youtube.com/embed/c-bemNZ-IqA" style="border:0px #ffffff none;" name="Open Science Video" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="400px" width="600px" allowfullscreen></iframe>```

Turning into:
<iframe src="https://www.youtube.com/embed/c-bemNZ-IqA" style="border:0px #ffffff none;" name="Open Science Video" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="400px" width="600px" allowfullscreen></iframe>


### Google Slides

Here's how you embed Google Slides in Jupyter Book with the HTML iframe:

* Go to your Google Slides presentation and click on the "File" button in the top-left corner of the screen.

* Click on "share" and select "Publish to the web"

* Select "Embed" and click "Publish"

* Open your Markdown file where you want to embed the Google Slides presentation.

* Copy the HTML-code, which could result in something like this:

`<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTJvUAN-dg7r7Dbj-KpxcNO6ssd7akDQjBbHzhTTBBU7zSBZ4sTfjYPtHZL6V7GmM0VQvo6Aviu5oSG/embed?start=false&loop=false&delayms=10000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>`

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTJvUAN-dg7r7Dbj-KpxcNO6ssd7akDQjBbHzhTTBBU7zSBZ4sTfjYPtHZL6V7GmM0VQvo6Aviu5oSG/embed?start=false&loop=false&delayms=10000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

Note that the width and height of the iframe can be adjusted to fit your specific use case. You may also want to adjust the styling of the iframe to match your Jupyter Book's visual design better.


### GIFs

Here's an example on how to implement GIFs in Jupyter Books:

`<iframe src="link/to/your/gif/file.gif" width="240" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>'`

Again, replace "link/to/your/gif/file.gif" with the URL or file path to your GIF.

Example: `<iframe src="https://giphy.com/embed/l5s71uAp3CzKwxwkoZ" width="240" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>`

Result:
<iframe src="https://giphy.com/embed/l5s71uAp3CzKwxwkoZ" width="240" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

```{note}
Note that if you're using a local file path, the path should be relative to the location of the Markdown file that you're embedding the GIF in. If you're using a URL, it should be a direct link to the GIF file.
```

___

There are plenty of other datatypes you can add! This section is only a short introduction to the embedding of media.

## Next section:
In the next section, you will learn how to integrate citations and bibliographies.
