# Introduktion till HTML

Du kanske undrar vad en mall är?

En mall är en fil som vi kan återanvända för att presentera information med olika innehåll i ett konsekvent format – till exempel kan du använda en mall för att hjälpa dig att skriva ett brev. För även om varje brev kan innehålla olika meddelanden och adresseras till olika personer, kommer de att dela samma format.

En Django-malls format skrivs på ett språk som heter HTML (det är den HTML vi nämnde i det första kapitlet, **Hur Internet fungerar**).

## Vad är HTML?

HTML är kod som tolkas av din webbläsare – till exempel Chrome, Firefox eller Safari – för att visa en webbsida för användaren.

HTML står för "HyperText Markup Language". **HyperText** betyder att det är en typ av text som stöder hyperlänkar mellan sidor. **Markup** betyder att vi har tagit ett dokument och markerat det med kod för att berätta något (i det här fallet, en webbläsare) hur man tolkar sidan. HTML-kod är byggd med **taggar**, var och en som börjar med `<` och slutar med `>`. Dessa taggar representerar markup-**element**.

## Din första mall!

Att skapa en mall innebär att skapa en mallfil. Allt är en fil, eller hur? Du har förmodligen märkt detta redan.

Mallar sparas i katalogen `blog/templates/blog` . Så skapa först en katalog som heter `templates` i katalogen blog. Skapa därefter en annan katalog som heter `blog` i din mallkatalog:

    blog
    └───templates
        └───blog
    

(Du kanske undrar varför vi behöver två kataloger som båda heter `blog` – som du kommer att upptäcka senare är detta en användbar namnkonvention som gör livet lättare när saker och ting börjar bli mer komplicerade.)

Skapa nu filen `post_list.html` (lämna den tom för nu) i katalogen `blog/templates/blog` .

Se nu hur din webbplats ser ut: http://127.0.0.1:8000/

> Om du fortfarande får ett fel `TemplateDoesNotExist`, försök att starta om din server. Gå till kommandoraden, stoppa servern genom att trycka på Ctrl+C (Control- och C-tangenten tillsammans) och starta den igen genom att köra kommandot `python manage.py runserver`.

![Figur 11.1](images/step1.png)

No error anymore! Congratulations :) However, your website isn't actually publishing anything except an empty page, because your template is empty too. We need to fix that.

Open the new file in the code editor, and add the following:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<html>
<body>
    <p>Hi there!</p>
    <p>It works!</p>
</body>
</html>
```

So how does your website look now? Visit it to find out: http://127.0.0.1:8000/

![Figur 11.2](images/step3.png)

It worked! Nice work there :)

* The most basic tag, `<html>`, is always the beginning of any web page and `</html>` is always the end. As you can see, the whole content of the website goes between the beginning tag `<html>` and closing tag `</html>`
* `<p>` is a tag for paragraph elements; `</p>` closes each paragraph

## Head and body

Each HTML page is also divided into two elements: **head** and **body**.

* **head** is an element that contains information about the document that is not displayed on the screen.

* **body** is an element that contains everything else that is displayed as part of the web page.

We use `<head>` to tell the browser about the configuration of the page, and `<body>` to tell it what's actually on the page.

For example, you can put a web page title element inside the `<head>`, like this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<html>
    <head>
        <title>Ola's blog</title>
    </head>
    <body>
        <p>Hi there!</p>
        <p>It works!</p>
    </body>
</html>
```

Save the file and refresh your page.

![Figur 11.3](images/step4.png)

Notice how the browser has understood that "Ola's blog" is the title of your page? It has interpreted `<title>Ola's blog</title>` and placed the text in the title bar of your browser (it will also be used for bookmarks and so on).

Probably you have also noticed that each opening tag is matched by a *closing tag*, with a `/`, and that elements are *nested* (i.e. you can't close a particular tag until all the ones that were inside it have been closed too).

It's like putting things into boxes. You have one big box, `<html></html>`; inside it there is `<body></body>`, and that contains still smaller boxes: `<p></p>`.

You need to follow these rules of *closing* tags, and of *nesting* elements – if you don't, the browser may not be able to interpret them properly and your page will display incorrectly.

## Customize your template

You can now have a little fun and try to customize your template! Here are a few useful tags for that:

* `<h1>A heading</h1>` for your most important heading
* `<h2>A sub-heading</h2>` for a heading at the next level
* `<h3>A sub-sub-heading</h3>` …and so on, up to `<h6>`
* `<p>A paragraph of text</p>`
* `<em>text</em>` emphasizes your text
* `<strong>text</strong>` strongly emphasizes your text
* `<br>` goes to another line (you can't put anything inside br and there's no closing tag)
* `<a href="https://djangogirls.org">link</a>` creates a link
* `<ul><li>first item</li><li>second item</li></ul>` makes a list, just like this one!
* `<div></div>` defines a section of the page

Here's an example of a full template, copy and paste it into `blog/templates/blog/post_list.html`:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<html>
    <head>
        <title>Django Girls blog</title>
    </head>
    <body>
        <div>
            <h1><a href="/">Django Girls Blog</a></h1>
        </div>

        <div>
            <p>published: 14.06.2014, 12:14</p>
            <h2><a href="">My first post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
        </div>

        <div>
            <p>published: 14.06.2014, 12:14</p>
            <h2><a href="">My second post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut f.</p>
        </div>
    </body>
</html>
```

We've created three `div` sections here.

* The first `div` element contains the title of our blog – it's a heading and a link
* Another two `div` elements contain our blog posts with a published date, `h2` with a post title that is clickable and two `p`s (paragraph) of text, one for the date and one for our blog post.

It gives us this effect:

![Figur 11.4](images/step6.png)

Yaaay! But so far, our template only ever displays exactly **the same information** – whereas earlier we were talking about templates as allowing us to display **different** information in the **same format**.

What we really want to do is display real posts added in our Django admin – and that's where we're going next.

## One more thing: deploy!

It'd be good to see all this out and live on the Internet, right? Let's do another PythonAnywhere deploy:

### Commit, and push your code up to GitHub

First off, let's see what files have changed since we last deployed (run these commands locally, not on PythonAnywhere):

{% filename %}command-line{% endfilename %}

    $ git status
    

Make sure you're in the `djangogirls` directory and let's tell `git` to include all the changes in this directory:

{% filename %}command-line{% endfilename %}

    $ git add --all .
    

> **Note** `--all` means that `git` will also recognize if you've deleted files (by default, it only recognizes new/modified files). Also remember (from chapter 3) that `.` means the current directory.

Before we upload all the files, let's check what `git` will be uploading (all the files that `git` will upload should now appear in green):

{% filename %}command-line{% endfilename %}

    $ git status
    

We're almost there, now it's time to tell it to save this change in its history. We're going to give it a "commit message" where we describe what we've changed. You can type anything you'd like at this stage, but it's helpful to type something descriptive so that you can remember what you've done in the future.

{% filename %}command-line{% endfilename %}

    $ git commit -m "Changed the HTML for the site."
    

> **Note** Make sure you use double quotes around the commit message.

Once we've done that, we upload (push) our changes up to GitHub:

{% filename %}command-line{% endfilename %}

    $ git push
    

### Pull your new code down to PythonAnywhere, and reload your web app

* Open up the [PythonAnywhere consoles page](https://www.pythonanywhere.com/consoles/) and go to your **Bash console** (or start a new one). Then, run:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ cd ~/<your-pythonanywhere-domain>.pythonanywhere.com
    $ git pull
    [...]
    

You'll need to substitute `<your-pythonanywhere-domain>` with your actual PythonAnywhere subdomain name, without the angle-brackets. Your subdomain name is normally your PythonAnywhere user name, but in some cases it might be a bit different (such as if your user name contains capital letters). So if this command doesn't work, use the `ls` (list files) command to find your actual subdomain/folder name, and then `cd` to there.

Now watch your code get downloaded. If you want to check that it's arrived, you can hop over to the **"Files" page** and view your code on PythonAnywhere (you can reach other PythonAnywhere pages from the menu button on the console page).

* Finally, hop on over to the ["Web" page](https://www.pythonanywhere.com/web_app_setup/) and hit **Reload** on your web app.

Your update should be live! Go ahead and refresh your website in the browser. Changes should be visible. :)