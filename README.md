Measurement
===========

This is a Ruby library for measurements that include units.
There are quite a few measurement/units libraries in Ruby, but this one is mine.
It's based primarily on ideas from the Scala [Squants](http://www.squants.com/) library.
However, we don't include a separate class for each unit.
Instead, we have a class for each measurement type, with units expressed as strings.

One of my goals with this library is to have something I can port to
my [Stone programming language](https://www.stone-lang.org) in the future.
That means that types will play an important role.
That's a bit unusual for a Ruby library,
so I'll likely make some different choices than other Ruby measurement/units libraries.


Installation
------------

Add this line to your application's Gemfile:

~~~ ruby
gem 'measurement-ruby'
~~~

And then execute:

~~~ shell
bundle
~~~


Usage
-----

~~~ ruby
length = Measurement::Length.new(12, "inches")
width = Measurement::Length.new(12, "in")
area = length * width
area.class  #=> Measurement::Area
area.to_s  #=> "144 square inches"
area.in("ft^2").to_s  #=> "1 ft^2"
height = Measurement::Length.new(2, "ft")
volume = area * height
volume.class  #=> Measurement::Volume
volume.to_s  #=> "3456 cubic inches"
volume.in("gallons").to_s  #=> "14.96104 gallons"
volume.in("liters").to_s  #=> "56.6336971169 liters"
~~~


Measurements
------------

I intend to include the following measurement types:

* Time
* Frequency
* Length (Distance, Width, Height)
* Area
* Volume
* Mass
* Bits (Bytes)
* Velocity (Speed)
* Acceleration
* Force
* Pressure
* Energy
* Power
* Current
* Voltage
* Resistance
* Temperature
* Angle
* Solid Angle


Contributing
------------

1. Fork the repository
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Add your changes
4. Make sure your changes are thoroughly tested
5. Make sure all the tests pass (`rspec` or `rake spec`)
6. Commit your changes (`git commit -am 'Add some feature'`)
7. Push to the branch (`git push origin my-new-feature`)
8. Create a Pull Request against my GitHub repo


License
-------

This software is released under the MIT license. See the [LICENSE](/LICENSE) file for full details.


Copyright
---------

Copyright (c) 2018 BoochTek, LLC
Copyright (c) 2018 Craig Buchek
