SpreeFancy
==========

SpreeFancy is a theme that can be applied to an existing spree application. It's intended as a starting point to show how a barebones Spree application can be easily modified to give a nice look and feel. As a special bonus it uses a responsive design so looks good on mobile devices as well as on larger screens.

If you'd like to see the theme in action, you can register for your own personal [online sandbox](http://spreecommerce.com/demo) which uses the same theme.

Installation
============

Themes in Spree are typically implemented as [Spree extensions](http://guides.spreecommerce.com/developer/extensions_tutorial.html). To use the theme you will need an existing Spree application running Spree version 1.3 or higher. If you are unsure of how to do this you can find instructions on how to create a simple Spree application in the [Spree README](https://github.com/spree/spree).

Once you have a rails application running Spree, it's a simple three step process to install the spree_fancy extension.

If you're using Spree 1.3, you will need to add the gem to your Gemfile using
this line:

```
gem 'spree_fancy', :github => 'spree/spree_fancy', :branch => '1-3-stable'
```

If you are using Spree's master branch, then use this line:

```
gem 'spree_fancy', :github => 'spree/spree_fancy'
```

Then install the gem via Bundler:

```
$ bundle install
```

Finally, you need to run spree_fancy's installer:

```
$ bundle exec rails g spree_fancy:install
```
This copies over the migrations from the extension into your application, and sets up asset pipeline require statements for `spree_fancy`.

Usage
=====

This theme alters the look and feel of the spree frontend, using the [bxSlider](http://bxslider.com/) jQuery plugin to present products on the front page. Products can appear in any of the 3 sliders: "Slider", "Featured" and "Latest". The plugin adds 3 taxonomies to control which products appear in the sliders. To try these out, sign in to the backend and try adding/removing the taxonomies to/from products and refresh the store front page to see how this affects the sliders.

This is achieved by overriding the index action in the Spree::HomeController using a Decorator. Have a look at the [Decorators Guide](http://guides.spreecommerce.com/developer/view.html) for more information about using decorators to customize your application's logic.

Customization
=============

In order to changeyour CSS and Javascript you will want to make a local copy and make your changes there.

For changing the variables there is a file pre-made for this.  To change the variables use the variables_override.css.scss and remove the !default

What you would see in Spree Fancy
https://github.com/spree/spree_fancy/blob/master/app/assets/stylesheets/spree/fancy/variables.css.scss
$c_green:       #8dba53 !default;  /* Spree green    */
$c_red:         #e45353 !default;  /* Error red      */
$c_blue:        #50A2F3 !default;
$c_orange:      #ff9600 !default;

What you would do in your App
YourApp/app/assets/stylesheets/spre/fancy/variables_override.css.scss
$c_green:       #399E48;  /* lighter green    */
$c_red:         #e45353 !default;   */
$c_blue:        #F68D3C;
$c_orange:      #F16521;  

For CSS classes and for Javascript files just make a local copy and edit that.

What you would see in Spree Fancy
https://github.com/spree/spree_fancy/blob/master/app/assets/stylesheets/spree/fancy/components/_slider.scss
#home-slider {
  h1 {
    font-size: 24px !important;
    font-weight: 600 !important;
  }

What you would edit in your App
Yourapp/app/assets/stylesheets/spree/fancy/components/_slider.scss
#home-slider {
  h1 {
    font-size: 40px !important;
    font-weight: 600 !important;
  }


Creating Your Own Extensions
============================

To learn more about creating your own extensions, have a look in the [Spree extensions tutorial](http://guides.spreecommerce.com/developer/extensions_tutorial.html)

Copyright (c) 2012-2013 Spree Commerce Inc., released under the New BSD License
