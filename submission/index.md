---
layout: page
title: Submit a Post
author: joe_morgan
tags: [post submission, how-to, github, email submission]
comments: false
image:
  feature: shapes-4.png
---

{% include _toc.html %}

Maybe you have an idea for how to apply devops principles to your job, outside of the intersection of development and operations. Or maybe you disagree with something I've said on this site so vehemently that a simple comment isn't enough to properly shred my viewpoint. Maybe you just want all of the wealth and recognition that comes from contributing to an open source blog.

Well, why not author a post of your own? One of the neat things about this blog is that it <i>is</i> open source, and anyone can contribute. Given the intended reach of this site, there are a couple ways that you could write a post, depending on whether or not you're comfortable with <a href="https://github.com/" target="_blank" title="GitHub">GitHub</a>.

##Ways to Contribute##

###Fork the Repo on GitHub###

If you're a technologist or you're otherwise familiar with git and GitHub, you'll probably find it easiest to simply fork <a href="https://github.com/JoeMorgan/devopsfortherestofus" target="_blank" title="Devops for the Rest of Us on GitHub">the repository</a>, draft your content, and make a pull request.

This blog uses <a href="http://jekyllrb.com/" target="_blank" title="Jekyll &bull; Simple, blog-aware, static sites">Jekyll</a>, so you can draft your content using Markdown. New posts are stored in the /_posts folder, so just add a file and name it appropriately for the date of publication (e.g., the Hello World post for this blog is named "2015-08-23-hello-world.md").

Each post should have some YAML "front matter" at the top to tell Jekyll how to create the static page. This is really just simple metadata, and you can use one of the existing posts as a starting point. For example, the front matter for my Hello World post looks like this:

{% highlight html %} {% raw %}---
layout: post
title: Hello World
author: joe_morgan
excerpt: "Do you feel like you're on the outside of the devops movement, looking in? Are you excited about automation and measurement as tools to improve the way you work, but you don't typically play in the ops space? This is the place for you. Welcome to Devops for the Rest of Us."
tags: [devops, bizdevops, hello world, meta blog]
comments: true
---{% endraw %} {% endhighlight %}

You may notice that it includes a reference to author. If you don't want my ugly mug next to your post, you'll have to do one more thing before making your pull request: simply update /data/authors.yml with an entry for yourself, and if you want a bio picture, put it in the /images folder (with the file name listed under "avatar" in the authors.yml). You only have to do this once, even if you're planning on writing multiple posts.

That's probably all you'll need to update. Though if you had a good idea for improving the site, you could make edits elsewhere in the codebase, I suppose. We just might need to talk it through before I accept the request.

And please remember to follow the general [submission guidelines](#submission-guidelines).

That's it! Now you can list experience with Jekyll on your resume.

###Send Me Your Post Content###

Yup, the old school way. Since this is a simple static site, we're not going to deal with logins, draft states, and permissions. Unless you're [comfortable using GitHub](#fork-the-repo-on-github), the best way for your voice to be heard on the blog is to simply reach out to me with your idea.

You can draft the post content over <a href="mailto:{{ site.owner.email }}" target="_blank">email</a>, along with some info about you for the sidebar (name, email, bio, an avatar picture to use, and any social info you want displayed). 

Assuming you've followed the general [submission guidelines](#submission-guidelines), I'll draft the post and let you know when it's live. Easy, no?

##Submission Guidelines##
1. Content in some way relates to devops
2. Nothing derogatory, spiteful, or inflammatory; i.e., no trolling
3. Opinion pieces are okay (encouraged, even!)