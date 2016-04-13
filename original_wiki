'''Ruby''' is a dynamic, reflective, object-oriented, general-purpose programming language. It was designed and developed in the mid-1990s by Yukihiro "Matz" Matsumoto in Japan.

__TOC__

== Code Organization ==
If possible, order your code as follows:
* boilerplate (only if absolutely necessary)
* require statements
* include statements
* class and module definitions
* constants
** public methods
** protected methods
** private methods
* main program section
* testing code

For consistency, order your methods by alphabetical order. For new and future developers, it is far more straightforward to sort by method names instead of grouping them semantically. The same applies when declaring constants.

== Naming ==
* Class and module names should be in camel-case.
** Class names should be nouns.
**Mixins (modules) should be adjectives (eg. Enumerable, Comparable, Taggable).
* Constants should be all upper-case, separated by underscores.
* Attributes and methods should be all lower-case, separated by underscores.
** Attributes should be nouns
** Methods should include a verb

== Formatting ==
* Indent code with two spaces (soft tab). This is a marked difference from Java's four spaces.
* NEVER use hard tabs. You cannot (and should not) expect everyone on the team to use the same IDE or client as you.
* For the same reason, kindly observe an 80-char limit per line of code.
* Ruby allows you to call methods without parentheses. Do this only when calling methods without arguments. The following methods, however, are exceptions to this:
** Kernel#require
** Module#include
** Kernel#p
** attr_*
 require(SomeModule)           # NO!
 require SomeModule            # OK
 include(Mixin)                # NO!
 include Mixin                 # OK

 p("This is a test")           # OK
 p "This is another test"      # OK

 array = [1, 2, 3]
 array.first                   # OK, returns 1
 array.include?(4)             # OK, returns true
 array.include? 4              # NO!!!
 array.slice(1, 2)             # OK, returns [2, 3]
 array.slice 1, 2              # NO!!!
* Use spaces around operators.
 # BAD STYLE
 bottles_of_beer_on_the_wall=99
 bottles_to_take=1
 bottles_of_beer_on_the_wall-=bottles_to_take

 # GOOD STYLE
 bottles_of_beer_on_the_wall = 99
 bottles_to_take = 1
 bottles_of_beer_on_the_wall -= bottles_to_take

 # BETTER STYLE
 bottles_of_beer_on_the_wall  = 99
 bottles_to_take              = 1
 bottles_of_beer_on_the_wall -= bottles_to_take
* Use an empty line before the return value of a method (unless it only has one line), and an empty line between defs.
 # BAD STYLE
 def grade_school_add(a, b)
   a+b
 end
 def grade_school_subtract(a, b)
   if a<b
     raise("You can't do this!")
   end
   a-b
 end

 # GOOD STYLE
 def grade_school_add(a, b)
   a + b
 end

 def grade_school_subtract(a, b)
   if a < b
     raise("You can't do this!")
   end

   a - b
 end
* Always put a whitespace after commas.
* Other style guides recommend whitespaces after ''{'' and before ''}''; however, considering that we are already limited to 80 chars per line, we do not observe this for ''{'' and ''}''.
* For hashes, while other style guides are ambivalent, we actively recommend using ''=>'' instead of colons. This makes it easier to distinguish whether a hash key is a symbol or a variable.
* Unless there are circumstances preventing it, use double-quotes to delimit strings.
 [:na, :na, "na", :na, {:heyhey => "goodbye"}]      # OK
 [:na,:na,"na",:na,{:heyhey => "goodbye"}]          # NO!!!
 [:na,:na,"na",:na,{ :heyhey => "goodbye" }]        # STOP!
 [:na,:na,"na",:na,{ heyhey: "goodbye" }]           # PLEASE!
 [:na,:na,"na",:na,{ heyhey: 'goodbye' }]           # WHY ARE YOU DOING THIS?!?
* When dealing with code blocks, use the ''{'' and ''}'' delimiters only when the code is a one-liner and does not exceed the 80-char limit. Otherwise, use ''do'' and ''end''.
 array = [1, 2, 3]
 array.each{|element| puts element}
 array.each do |element|
   puts element
   puts "element"
 end

== Boolean Values ==
Ruby considers nil and false to be false, and all other values to be true. This means that some values, which, in other languages evaluate to false, may evaluate to true in Ruby. Take extra care when checking these values.

 p true    ? 17 : 21      # -> 17
 p false   ? 17 : 21      # -> 21

 p nil     ? 17 : 21      # -> 21
 p ""      ? 17 : 21      # -> 17
 p "null"  ? 17 : 21      # -> 17
 p "true"  ? 17 : 21      # -> 17
 p "false" ? 17 : 21      # -> 17

 p 0       ? 17 : 21      # -> 17
 p 1       ? 17 : 21      # -> 17

== Boolean Logic Operators ==
Although Ruby allows ''and'' and ''or'' operators, do NOT use these. Stick to ''&&'' and ''||'', as these do not bind in predictable ways.
 puts nil || "foo"      # evaluates to puts(nil || "foo"), prints "foo"
 puts nil or "foo"      # evaluates to (puts nil) || "foo", prints nil

Also, instead of using ''and'' between two function calls, use ''if''.
 # BAD STYLE
 do_something and do_something_else
 do_another_thing and return

 # GOOD STYLE
 if do_something
   # here, it is clear that do_something_else depends on do_something succeeding
   do_something_else
 end

 return if do_another_thing

== Default Parameter Values ==
You can specify values for variables as part of a method's parameter list.
 def custom_tag(tag, text, attributes={})
   ...
 end

Default parameter values are particularly useful when a method has lots of parameters, most of which only rarely need to have a different value. Using default parameters allows you to avoid having to specify values for every method call. Take care, however, against overusing it. In cases where a function has lots of parameters with values, it might be better to just use an options hash. For example, the following code:
 def custom_button_tag(url, class = "btn", title = "", icon = "pencil", method = "POST")
   ..
 end

might be better rewritten as:
 def custom_button_tag(url, options={})
   class  = options[:class]  || "btn"
   icon   = options[:icon]   || "pencil"
   method = options[:method] || "POST"
   title  = options[:title]  || ""

   ...
 end

Note that, when assigning default parameter values, we do NOT put whitespaces around the assignment operator.

== References ==
* MacDonald, Ian. [[http://www.caliban.org/ruby/rubyguide.shtml The Unofficial Ruby Usage Guide]]
* Pytel, Chad and Saleh, Tammer. [[http://http://railsantipatterns.com Rails AntiPatterns]]
