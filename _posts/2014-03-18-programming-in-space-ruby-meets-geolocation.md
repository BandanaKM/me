---
layout: post
title: "Programming in Space: Ruby Meets Geolocation"
description: "Understanding Ruby's Current and Future Capacity To Work With Geographic Information"
modified: 2014-01-18 12:18:10 -0400
tags: [Geolocation, Maps, Ruby, Rails]
image:
  feature: 
  credit: 
  creditlink: 
comments: true
share: true 
---


Understanding Ruby's Current and Future Capacity To Work With Geographic Information

Maps are a useful way to represent information, and have become increasingly popular in web based applications. Ruby mapping frameworks are not as mature as other platforms like GeoDjango, a framework written in Python that supports a suite of tools for spatial applications for Django.

Still, with the rise of open source projects that rely on millions of programmers writing in multiple languages to meet a common aim, understanding Ruby’s current (and future) capacity to work with maps and geographic information is definitely a worthwhile pursuit.

After some research, I’ve found some of the following tools and gems for Ruby (and Rails), that might be useful for Rubyists embarking on map-based and location-aware apps:

# [Ruby Geocoder](http://www.rubygeocoder.com/)

This simple and easy to use gem provides the ability to geocode an object by street or IP address. Geocoding is the process of find geographic coordinates from other data, such as street data, landmarks, and postal codes. The Geocoder gem specifically works with Rails and comes with a video tutorial. 

# [Graticule](http://graticule.rubyforge.org/)

Graticule allows you to geocode addresses and perform distance calculations. It supports a number of API’s, including: Yahoo, Google, Geocoder.us, PostCodeAnywhere, and MegaCarta. It also comes with a plugin for Rails that makes your applications location-aware.

# [Geokit](http://geokit.rubyforge.org/index.html)

Geokit is a Ruby gem and Rails plugin for map-based applications. Geokit can calculate distance between any two points in the world, find places within a certain radius, find the latitude and longitude of a given location. It supports a number of APIs including Google, Yahoo, Geonames, Geocoder.us, Geonames and more to geocode addresses.

# [RGeo](http://dazuma.github.io/rgeo/rdoc/)

RGeo is a geospatial library for creating and and analyzing geographic data. The goal is to make Ruby a world-class platform for location-based application development and performing geometric analysis. Through RGeo you can represent vector data—distinct objects in space like points, lines, and polygons—in Ruby applications, and also run a number of operations for geometric analysis that older platforms do not support. For more advanced purposes, RGeo supports spatial analysis operations like computing length and area.

# [GeoRuby](http://georuby.rubyforge.org/)

GeoRuby provides data types intended to hold data from PostGIS and the spatial extensions of MySQL (both of these allow you to run database queries on geographic objects). GeoRuby is a bit older than RGeo and  does not allow for geometric analysis and algorithms, such as computing the size of objects.

# [Cartographie](https://www.ruby-toolbox.com/projects/cartographie/popularity)

Cartographie is a gem that helps you use Google’s static maps API, a way to embed a Google map on your website without using JavaScript or dynamic page loading. The static map takes an HTTP or URL request and returns it as an image. Simply put, the Cartographie gem helps make these maps beautiful.

In future posts, I’ll be writing more on web applications that use Ruby and Rails for spatial and map-based data, with a focus on coding for good. Maps are a dynamic tool to meet human needs of our time; Ruby is in need of a community to support these ever expanding goals of map based information and its real world applications, and I feel extremely fortunate to be a part.
