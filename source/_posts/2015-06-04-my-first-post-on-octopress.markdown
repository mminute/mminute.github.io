---
layout: post
title: "When Constants are NOT Constant"
date: 2015-06-04 21:34:41 -0400
comments: true
categories: "Flatiron&nbsp;School"
---
The speed of light.

Avogadro's number.

Planck's constant.

The mass of an electron.

I thought that I understood constants.  Unchanging. Immutable.  Then Ruby went and fucked it up.

My understanding of constants in Ruby was that they are represented by a capitalized bareword (often all upper case) which, once defined, would cause Ruby to pitch a fit if you were to try to reassign its value.  Makes sense, right?  So when I saw this I was a bit confused:

```
class Shoe
  BRANDS = []

  def initialize(brand)
    @brand = brand
    if BRANDS.include?(@brand) == false
    BRANDS << @brand
    end
  end
end
```

Wait.. whaaaaaa????

```
BRANDS << @brand
```

Aren't we changing what BRAND represents?
Yes and no.
We are NOT changing the object to which the bareword "BRANDS" points.
We ARE changing the contents of that array, or what I formerly thought of as the value for "BRANDS".

```
BRANDS = []
BRANDS.object_id #=> 70132206506080
BRANDS << "LA Gear"
BRANDS << "FILA"
BRANDS #=> ["LA Gear", "FILA"]
BRANDS.object_id #=> 70132206506080
```

But, wait!  There's more!

So, while the value of PI might be the same in your home as it is in Intercourse, Pennsylvania,  Fucking, Austria,  and Wetwang, Yorkshire UK (all real places, btw), a constant may not be the same everywhere in your code.  Let's try this: 


```
PIE = ["mmmmmm","piiiiiiiieeeeeee"]

class TastyStuff
  PIE = ["Pecan", "Apple", "Pumpkin"]

  def initialize(name)
    if PIE.include?(name)
      puts "Nom!"
    end
  end
end

my_treat = TastyStuff.new("Pecan") #=> "Nom!"

PIE #=> ["mmmmmm","piiiiiiiieeeeeee"]
```

So now we have two "PIE"s?
Hello Namespacing!  How're the wife and kids?!


```
PIE = ["mmmmmm","piiiiiiiieeeeeee"]

class TastyStuff
  PIE = ["Pecan", "Apple", "Pumpkin"]

  def initialize(name)
    if PIE.include?(name)
      puts "Nom!"
    end
  end
end

my_treat = TastyStuff.new("Pecan") #=> "Nom!"

PIE #=> ["mmmmmm","piiiiiiiieeeeeee"]
TastyStuff::PIE #=> ["Pecan", "Apple", "Pumpkin"]
```

What happens if we get rid of the "PIE" inside the class?

```
PIE = ["Pecan", "Apple", "Pumpkin"]

class TastyStuff
  def initialize(name)
    if PIE.include?(name)
      puts "Nom!"
    end
  end
end

my_treat = TastyStuff.new("Pecan") #=> "Nom!"

PIE #=> ["Pecan", "Apple", "Pumpkin"]
```

But if we reverse it...

```
class TastyStuff
  PIE = ["Pecan", "Apple", "Pumpkin"]

  def initialize(name)
    if PIE.include?(name)
      puts "Nom!"
    end
  end
end

my_treat = TastyStuff.new("Pecan") #=> "Nom!"

PIE #=> uninitialized constant PIE (NameError)
```

Sooooooo... now we can't call "PIE" from outside of the class?   It only works from within the class?  I guess we could call it a 'Class Constant'?  Yeah, let's call it a Class Constant because, well, that's what it's called.



----------------------------------------------------------------------------------------

Let's summarize:

- Constants can only be set to point to an object once.
```
LYRICS = ["Nah Nah Nah Nah"]
LYRICS = ["Hey Hey Hey, Goodbye"]
#=>2: warning: already initialized constant LYRICS
#=>1: warning: previous definition of LYRICS was here
```
- The object to which a constant points CAN be changed.
```
LYRICS = ["Nah Nah Nah Nah"]
LYRICS << "Hey Hey Hey, Goodbye"
#=> ["Nah Nah Nah Nah" , "Hey Hey Hey, Goodbye"]
```
- Constants have a scope / are namespaced.
```
LYRICS = ["Nah Nah Nah Nah"]

class Tunes
  LYRICS = ["Hey Hey Hey, Goodbye"]
end

LYRICS #=> ["Nah Nah Nah Nah"]
Tunes::LYRICS #=> ["Hey Hey Hey, Goodbye"]
```



