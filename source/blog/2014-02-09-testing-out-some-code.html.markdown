---
title: Testing Out Some Code
date: 2014-02-09 21:47 UTC
tags:
---

So I am using this article to test out some markdown features, especially the markup of code examples in my blog articles. I hope to use this blog to illustrate ideas and concepts I am learning in school as well as showcase some code snippits or useful information that I find. so on with the testing!

~~~ ruby
def index
  @cars = Car.all

  respond_to do |format|
    format.html # index.html.erb
    format.json { render json: @cars }
  end
end
~~~

This is an example with some inline code examples. I may want to show a `<span>` tag in there or something like it. I could even use keyboard shortcuts like `Opt + A`.