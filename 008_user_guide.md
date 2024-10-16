---
layout: default
title: User Guide
number: 8
---

# User Guide

## Establish a Repository with Your Copy of MinPub In It

The first thing you’ll need to do—to build your website—is to create a copy of our MinPub template that you can alter to suit your needs and put into something GitHub calls ‘a repository.’ A repository is just a collection of files within a larger project (in this case MinPub). So in this step you will create a clone copy of the MinPub files, within a repository you will name as your own.  To create the site, you’ll then be revising these files to reflect your content (adding all the elements of your edition: the source, your commentary, footnotes, etc.) You will revise these files to make your website.  To create your Repository, with your new copy of the MinPub template in it:

- ***Sign in to GitHub*** - If you don’t already have an account, create one. Go to [GitHub](https://github.com) and select “sign up” at the top right corner.
- ***Go to the MinPub Repository*** - This is where you will find all the MinPub files: [ScholarMinPub GitHub Repository](https://github.com/DerDoktorFaust/ScholarMinPub).
- ***Create Your Own Repository*** - Click on the big green button on the top right of the screen ("Use this Template") It will provide you with two options. Choose ”Create a New Repository.”
- ***Choose a Name for your Brand New MinPub Project*** - This should be LASTNAME-FIRSTNAME-HIST-CLASSNUMBER
- ***Set the Preferences*** - The default setting is public repository. Do not change this, as you can only deploy a website if the repository is public.
- ***Click Create Repository***

## Initial Testing of Your Site

So your new copy of MinPub already can be converted into a website, using GitHub’s tools. It’s just a blank website (for now), since you haven’t added any content. Still, it makes sense to make sure you can deploy your site before you put more work into it. Here’s how.

- ***Go to the Settings Tab and Choose ‘Pages’*** - It’s in the top left bar.
- ***Set the Site to Deploy from Main Branch*** - Click on the Save button. The "branch” refers to your unique version of the MinPub repository. The main branch is considered the most simple, stable, and deployable branch. By selecting the main branch, all your edits will be merged and displayed on your website.
- ***Reload the Page*** - The link to your website will appear at the top of the same page.  This may take several minutes, so don’t worry if your link isn’t immediately generated.
- ***Copy and Store Your New URL So You Have It Handy*** - Copy the link, then click on the ‘Code’ page (top left).  Find the ‘About’ section (on the right). Click on the Settings button, which is just to the right of “About” and looks like a gear. Then paste the URL (the website’s address) in the “Website” line to always have it at hand.  
- ***Set Your Site baseurl***
    - Set your Config.yml File - You can find the “config.yml” folder under the “Code” button at the top left hand of the screen. The “config.yml” folder is near the bottom of the page.
    - Replace the content of the line "baseurl" in the config.yml folder with the name of your repository, which is the name you selected when you initially created your own repository.  Be sure to copy the name exactly (e.g., 'baseurl: "/ScholarMinPub"' --> 'baseurl: "LASTNAME-FIRSTNAME-HIST-CLASSNUMBER"').
    - Change the title of your project
    - Add your group members' names
- ***Click on the Link You Created in the Step Above*** - Your website should now load.

> [!WARNING] 
> Do not move files around in your directory structure. Do not alter ANY existing files except the _one_ time you change _config.yml and the numbered files where you put your content (i.e. files beginning with 001... 007).

## Adding Content

### Adding Text

To add text content:
- Click on one of the text files (001... 007)
- Click on the little pencil symbol in the top left
- On the page that opens, add your text
- Press the green button at the top that says "Commit Changes..."

Leave base titles alone that have the {% raw %} # Title {% endraw %} headings. To add second-level titles, use {% raw %} ## Second-Level Title {% endraw %}.

Also, do not change any text at the top of each file, everything that is between the ``` --- ``` symbols.

### Adding Links

To add a link, use the following code: ``` [text to describe the link or the website's name](url to the site) ```

### Adding Images

#### Uploading an Image to Your Site

To add an image you found on the internet, you first need to download the image to your computer. Then you need to add the image to your site:
- Navigate to the following directory: /media_files/images
- Click "Add File" at the top of the page
- Click "Upload Files"
- Drag and drop your downloaded file
- Press the green button "Commit Changes"

#### Create the Image Description File

- Navigate to the directory /media_files/_media_metadata
- Press the Add File button at the top left
- Select "Create New File"
- Name your file a descriptive name that makes sense based on the image

Copy and paste the following:


```
--- 

name: EmperorNapoleon
media_type: image

_title: Napoleon ler en costume du Sacre
description: Napoleon as the Emperor of France
creator: Francois Gerard
_date: 1805
source: Wikipedia

_path: /media_files/images/emperornapoleon.jpg 
layout: media_description

--- 
```


Change the information above to match your new image. Remember the "name" you give it above.


#### Add the Image to One of your Pages

Copy and paste the following to where you want the image to appear in your text file:

{% raw %}
{% assign media = site.media_metadata | where_exp: "item", "item.name == 'PrussianInfantryHohenfriedberg'" %}
{% include media.html pages=media %}
{% endraw %}

Now, change PrussianInfantryHohenfriedberg to the "name" you gave your image in the step above.

### Adding Video Files

#### Find Your Video and Get its URL

- Find a video on YouTube that you want to add.
- Click the Share button below the video
- Select "Embed"
- Copy the URL that appears in front of "src" but make sure not to include the quotation marks. (do not just press the Copy button that YouTube shows you--highlight the URL and copy it like it was regular text)

Example:

After following the steps above, YouTube gives you the following code:

{% raw %}
```
<iframe width="560" height="315" src="https://www.youtube.com/embed/PizUbOsjYm0?si=SukZvyQDpYvHldiR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```
{% endraw %}

Copy only the following:

{% raw %}
https://www.youtube.com/embed/PizUbOsjYm0?si=SukZvyQDpYvHldiR
{% endraw %}

#### Create Your Video Description File

- Navigate to the directory /media_files/_media_metadata
- Press the Add File button at the top left
- Select "Create New File"
- Name your file a descriptive name that makes sense based on the image

Copy and paste the following:

```
---

name: RiseOfPrussia
media_type: video

_title: Ten Minute History - Frederick the Great and the Rise of Prussia
description: Short video explaining the rise of Prussia
creator: History Matters
_date: 2019
source: YouTube

_path: https://www.youtube.com/embed/wzYfkezHp3k?si=qcH-0UDQp8mtTa8j
layout: media_description

---
```


Change the information above to match your new video. Remember the "name" you give it above.

#### Add the Video to One of your Pages

Copy and paste the following to where you want the video to appear in your text file:

{% raw %}
{% assign media = site.media_metadata | where_exp: "item", "item.name == 'RiseOfPrussia'" %}
{% include media.html pages=media %}
{% endraw %}

Now, change RiseOfPrussia to the "name" you gave your video in the step above.

### Adding a TimelineJS Timeline

- Create your timeline using TimelineJS
- In step 4 of the process, copy everything under the Embed heading (starting with <iframe... )
- Paste this where you want it to display on your site.

After {% raw %} <iframe {% endraw %} add the following: {% raw %} class='timeline-iframe' {% endraw %}.

Your final code should look exactly like this (except the "src" URL will be different):

```
<iframe class='timeline-iframe' src='https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=12ZNkEbnN4RnsWLrW2Ekpz2cQV_2QA-3WgJTP4WUKduk&font=Default&lang=en&initial_zoom=2&height=650' width='100%' height='650' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>
```