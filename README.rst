github-activity
===============

A JavaScript module to read and render a user's public github activity
as HTML.  

This javascript reads the public activity returned by 
``http://github.com/username.json`` as jsonp and renders it either to a
default or given html template.

Dependencies
------------
* JQuery
* underscore.js

How to use
----------

1. Define a container for results to be put in::

    <div id="#github-activity">
    </div>

2. Include underscore, jQuery and github_activity.js::

    <script src="/static/js/jquery.min.js"></script>
    <script src="/static/js/underscore-min.js"></script>
    <script src="/static/js/github_activity.js"></script>

3. Call ``GitHubActivity.show_activity(username, selector)`` to render
   activity::

    <script type="text/javascript" charset="utf-8">
        $(document).ready(function() {
            GithubActivity.show_activity('your_userid', '#github-activity');
        });
    </script>

4. Optionally, you can provide your own template html like this::

        GithubActivity.show_activity('your_userid', 
                                        '#github-activity',
                                        '#my-template');

Where ``'#my-template' is a selector for your provided template.  Look
at the output of::

https://github.com/your_username.json

to get an idea of the fields you can use in the template.
