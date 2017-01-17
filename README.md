# Kirby Twig Cheatsheet

FVSCH brings Twig templates to Kirby. 

https://github.com/fvsch/kirby-twig

Keep your code clean and reusable. However, it may not be clear on how to do certain things the Twig was as opposed to PHP.

## Child / subpages loop

Get children (eg. projects) loop:

    {% for project in page('projects').children.visible %}
    
I thought you would use `page.projects`. ¯\\\_(ツ)_/¯

## Thumbnails
    
Use Kirby's thumb function (eg for project loop above):

    <img src="{{ thumb(project.image, {'width': 300, 'height': 200} ).url }}">
    
## YAML    
    
Parse yaml "array":

Eg. In your site.md:

    ----

    Socialmedia:

    LinkedIn:
        url: https://www.linkedin.com/in/geoffyuen?trk=hp-identity-name

    Twitter:
        url: https://twitter.com/geoffyuen

    Codepen:
        url: http://codepen.io/geoffyuen/

    ----

Use this in your template .twig:

    {% for label, social in yaml(site.socialmedia) %}

`label` gives you the array key string (eg. LinkedIn). `social` gives you the url (eg. https://www.linkedin.com/in/geoffyuen?trk=hp-identity-name)
