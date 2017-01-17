# Kirby Twig Cheatsheet

https://github.com/fvsch/kirby-twig

Get subpages (eg. projects) loop:

    {% for project in page('projects').children.visible %}
    
Use Kirby's thumb function (eg for project loop above):

    <img src="{{ thumb(project.image, {'width': 300, 'height': 200} ).url }}">
    
Parse yaml "array":

Eg. In your content:
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
