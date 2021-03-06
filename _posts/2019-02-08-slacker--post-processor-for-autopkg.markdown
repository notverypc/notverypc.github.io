---
layout: post
title: "Slacker - Post Processor for AutoPkg"
date: 2019-02-08
author: notverypc
tags:
  - autopkg 
category: blog
blog: true
---
Back in December 2017 Graham Pugh wrote a slack notification post-processor for AutoPkg/JSSImporter.

<a href="https://grahamrpugh.com/2017/12/22/slack-for-autopkg-jssimporter.html">https://grahamrpugh.com/2017/12/22/slack-for-autopkg-jssimporter.html</a>

I really like this, but we use munki so I decided to adapt Graham’s post-processor for munki.

<a href="https://github.com/notverypc/autopkg-recipes/tree/master/PostProcessors">https://github.com/notverypc/autopkg-recipes/tree/master/PostProcessors</a>

The install/setup is the same as for Graham’s but as we aren’t using JSSImporter we’ll need to install the “requests” python library with `pip install requests`.

I added some additional customisation to the notifications which can be changed to suite you:
```
AUTOPKGICON = "https://avatars0.githubusercontent.com/u/5170557?s=200&v=4"
ICONEMOJI=":ghost:"
USERNAME = "AutoPKG"
```

<img src="{{site.baseurl}}/assets/img/slacker_notification.png">

Now during an AutoPkg run if an item is imported into Munki you’ll get a slack notification.

Further Development Ideas:
Changing Colour/Icon of the notifications depending on the item imported using the options available via the slack api

Thanks:
Based on Graham Pugh's slacker.py
<a href="https://github.com/grahampugh/recipes/blob/master/PostProcessors/slacker.py">https://github.com/grahampugh/recipes/blob/master/PostProcessors/slacker.py</a>

@thehill idea on macadmin slack - <a href="https://macadmins.slack.com/archives/CBF6D0B97/p1542379199001400">https://macadmins.slack.com/archives/CBF6D0B97/p1542379199001400</a>

 Takes elements from - 
 <a href="https://gist.github.com/devStepsize/b1b795309a217d24566dcc0ad136f784">https://gist.github.com/devStepsize/b1b795309a217d24566dcc0ad136f784</a>
<a href="https://github.com/autopkg/nmcspadden-recipes/blob/master/PostProcessors/Yo.py">https://github.com/autopkg/nmcspadden-recipes/blob/master/PostProcessors/Yo.py</a>

I Blame Pat for this....