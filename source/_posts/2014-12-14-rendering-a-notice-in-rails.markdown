---
layout: post
title: "Rendering a Notice in Rails"
date: 2014-12-14 23:31:08 -0500
comments: true
categories: Notices
---

Last week we had our science fair at the Flatiron School. It was nerve wracking, but an awesome and fun experience. The week prior was grueling. Whilst spending hours with my team building our app, I noticed something interesting about notices and errors.

The first place I rendered a notice was in the Sessions Controller. It was plain and simple, no problem.

``` ruby
def destroy
  session[:user_id] = nil
  redirect_to root_path, :notice => "You've been signed out!"
end
```
Great! Onto the next message, an error in my Landings Controller:

``` ruby
def create
  @user = User.find(params[:user_id])
  @landing = Landing.new(landing_params)
  if @landing.save
    redirect_to user_landing_path(@user, @landing)
  else
    render "new", :error => "Please fill in all fields!"
  end
end
```

But wait, this notice did not render. The render method doesn't take an alert/notice/error hash entry like the redirect_to method does. So, how do we make a flash appear on "render"?

```ruby
def create
  @user = User.find(params[:user_id])
  @landing = Landing.new(landing_params)
  if @landing.save
    redirect_to user_landing_path(@user, @landing)
  else
    flash.now[:error] = "Please fill in all fields!"
    render "new"
  end
end
```

Not too much hassel. We had to add one extra line before the render - `flash.now`. This makes the notice render on the current page.