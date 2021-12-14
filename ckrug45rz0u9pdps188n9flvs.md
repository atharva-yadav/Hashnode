## Create a Text Portrait using CSS

Hey, did you know, you can create beautiful text portraits of any image using CSS? Yes, within a few lines of CSS, we can create awesome text portraits. So, if you are one of those, who loves to play with CSS, then hold on. Within 2 minutes you will get to know how to create portraits using CSS.

Follow the below-mentioned steps to do the same:

## Step 1: Setting up the HTML

Create a document and fill it with a lot of text so that your webpage is filled with the text. If you want any random text, use the `lorem` property in HTML. 

But if you want a particular word to be repeated, use the  [JavaScript repeat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)  function as shown below.

```
<body>
    <p id="text"></p>
    <script>
      let str = "Hashnode ";
      document.getElementById("text").innerHTML = str.repeat(1000);
    </script>
  </body>
```

## Step 2: Set the background image (Using CSS)
While setting the background image,

1. Set background image using CSS `url()` function.
2. Add background-repeat equal to `no-repeat` to avoid repetition of the image.
3. Position your image in the centre
4. Reduce the space between lines for better visuals.


```
      p {
        line-height: 14px;
        /* You can URL of any image here*/
        background: url("https://cdn.hashnode.com/res/hashnode/image/upload/v1611902473383/CDyAuTy75.png?auto=compress"); 
        background-repeat: no-repeat;
        background-size: 40%;
        background-position: center;

      }
``` 


## Step 3: Clip text over image

After doing the above steps, you will notice that some part of the text is covered by the image, but we want to clip text over an image and the remaining text should be transparent. For accomplishing this, we will use the property called `-WebKit-text-fill-color`.

We need to clip our text so that the background of an image is painted with the foreground text. So we clipped text & for making it viewable we used background `-WebKit-text-fill-color`.



```
p {
    -webkit-background-clip: text;
    -webkit-text-fill-color: rgba(0, 0, 0, 0);
}
``` 

After that make some changes to fonts, background-size, according to your choice and that's all, your text portrait is ready. You will see this type of output as a result.


## Complete Code

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Text Portrait using CSS</title>

    <style>
      body {
        background: rgba(0, 0, 0, 0);
        overflow: hidden;
        font-family: "Segoe UI", sans-serif;
      }

      p {
        line-height: 14px;
        background: url("https://cdn.hashnode.com/res/hashnode/image/upload/v1611902473383/CDyAuTy75.png?auto=compress"); /* You need to add path of image from your PC*/
        background-repeat: no-repeat;
        background-position: center;
        width: 100%;
        
        -webkit-background-clip: text;
        -webkit-text-fill-color: rgba(0, 0, 0, 0);
      }
    </style>
  </head>

  <body>
    <p id="text"></p>
    <script>
      let str = "Hashnode ";
      document.getElementById("text").innerHTML = str.repeat(1000);
    </script>
  </body>
</html>
```

## See how it works

%[https://codepen.io/atharvayadav/pen/MWmXBrz]

Hope you found this helpful; If yes, please consider sharing it with other developers who may need this. You can also tell us your opinions, suggestions in below comment box.

