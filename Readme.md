## Alternatives, click these links for naming conventions in other languages.
<b>java programs</b> http://www.oracle.com/technetwork/java/codeconventions-135099.html
<br><b>c programs  </b>https://users.ece.cmu.edu/~eno/coding/CCodingStandard.html#names

Your language not on this list and important? open an issue and I will gladly add the convention.
<br>cheers, Michael Dimmitt
### Questions

  Aim to have just a single class/module per source file. Name the file name as the class/module, but replacing CamelCase with snake_case.

## Naming

> The only real difficulties in programming are cache invalidation and
> naming things. <br>
> -- Phil Karlton

  ### Quick Reference Section

  Github Repositories named by the ruby community seem to use snake case, ex: project_name.
  In particular, Github does not use snake case. Their repos with websites include "."'s, they use, ex: project-name.

  Use `snake_case` for naming files, e.g. `hello_world.rb`.

  Use `snake_case` for naming directories, e.g.
  `lib/hello_world/hello_world.rb`.

  Use `UpperCamelCase` (PascalCase) for classes and modules.  (Keep acronyms like HTTP, RFC, XML uppercase.)

  Use `snake_case` for symbols, methods and variables.
  Do not separate numbers from letters on symbols, methods and variables.

  Use `SCREAMING_SNAKE_CASE` for other constants.

  The names of predicate methods (methods that return a boolean value) should
  end in a question mark.  (i.e. `Array#empty?`). Methods that don't return a
  boolean, shouldn't end in a question mark.

  Avoid prefixing predicate methods with the auxiliary verbs such as `is`,
  `does`, or `can`.  These words are redundant and inconsistent with the style of
  boolean methods in the Ruby core library, such as `empty?` and `include?`.

  The names of potentially *dangerous* methods (i.e. methods that modify
  `self` or the arguments, `exit!` (doesn't run the finalizers like `exit`
  does), etc.) should end with an exclamation mark if there exists a safe
  version of that *dangerous* method.

  part 2 ...

  Define the non-bang (safe) method in terms of the bang (dangerous) one if
  possible.

  When defining binary operators, name the parameter `other`(`<<` and `[]` are
  exceptions to the rule, since their semantics are different).

  ## Naming Repeated, with examples for Referencing purposes
  Use `snake_case` for symbols, methods and variables.
  Do not separate numbers from letters on symbols, methods and variables.

  ```ruby
  # bad
  :some_sym_1

  # good
  :some_symbol1
  :some_symbol1

  def some_method1
    # some code
  end
  ```

  Use `UpperCamelCase` (PascalCase) for classes and modules.  (Keep acronyms like HTTP, RFC, XML uppercase.)

  ```ruby
  # bad

  # good
  class SomeClass
    # some code
  end

  class XMLSomething
    # some code
  end
  ```

  Use `SCREAMING_SNAKE_CASE` for other constants.

  ```ruby

  # good
  SOME_CONST = 5
  ```

  The names of predicate methods (methods that return a boolean value) should
  end in a question mark.  (i.e. `Array#empty?`). Methods that don't return a
  boolean, shouldn't end in a question mark.

  Avoid prefixing predicate methods with the auxiliary verbs such as `is`,
  `does`, or `can`.  These words are redundant and inconsistent with the style of
  boolean methods in the Ruby core library, such as `empty?` and `include?`.

  The names of potentially *dangerous* methods (i.e. methods that modify
  `self` or the arguments, `exit!` (doesn't run the finalizers like `exit`
  does), etc.) should end with an exclamation mark if there exists a safe
  version of that *dangerous* method.

  ```ruby
  # bad - there is no matching 'safe' method
  class Person
    def update!
    end
  end

  # good
  class Person
    def update
    end
  end

  # good
  class Person
    def update!
    end

    def update
    end
  end
  ```

  Define the non-bang (safe) method in terms of the bang (dangerous) one if
  possible.

  ```ruby
  class Array
    def flatten_once!
      res = []

      each do |e|
        [*e].each { |f| res << f }
      end

      replace(res)
    end

    def flatten_once
      dup.flatten_once!
    end
  end
  ```

  When defining binary operators, name the parameter `other`(`<<` and `[]` are
  exceptions to the rule, since their semantics are different).

  ```ruby
  def +(other)
    # body omitted
  end
  ```

## Comments

> Good code is its own best documentation. As you're about to add a
> comment, ask yourself, "How can I improve the code so that this
> comment isn't needed?" Improve the code and then document it to make
> it even clearer. <br>
> -- Steve McConnell

  Use one space between the leading `#` character of the comment and the text
  of the comment.

  Comments longer than a word are capitalized and use punctuation. Use [one
  space](https://en.wikipedia.org/wiki/Sentence_spacing) after periods.

  Keep existing comments up-to-date. An outdated comment is worse than no
  comment at all.

> Good code is like a good joke: it needs no explanation. <br>
> &mdash; old programmers maxim, through [Russ Olsen](http://eloquentruby.com/blog/2011/03/07/good-code-and-good-jokes/)

  Avoid writing comments to explain bad code. Refactor the code to make it
  self-explanatory. ("Do or do not&mdash;there is no try." Yoda)


<pre>
   ╔═══════════════════════╦═════════════╦════════════╦══════════════╦════════════╦════════════╗
   ║      PHP Project      ║   Classes   ║  Methods   ║  Properties  ║ Functions  ║ Variables  ║
   ╠═══════════════════════╬═════════════╬════════════╬══════════════╬════════════╬════════════╣
   ║ Akelos Framework      ║ PascalCase  ║ camelCase  ║ camelCase    ║ lower_case ║ lower_case ║
   ║ CakePHP Framework     ║ PascalCase  ║ camelCase  ║ camelCase    ║ camelCase  ║ camelCase  ║
   ║ CodeIgniter Framework ║ Proper_Case ║ lower_case ║ lower_case   ║ lower_case ║ lower_case ║
   ║ Concrete5 CMS         ║ PascalCase  ║ camelCase  ║ camelCase    ║ lower_case ║ lower_case ║
   ║ Doctrine ORM          ║ PascalCase  ║ camelCase  ║ camelCase    ║ camelCase  ║ camelCase  ║
   ║ Drupal CMS            ║ PascalCase  ║ camelCase  ║ camelCase    ║ lower_case ║ lower_case ║
   ║ Joomla CMS            ║ PascalCase  ║ camelCase  ║ camelCase    ║ camelCase  ║ camelCase  ║
   ║ modx CMS              ║ PascalCase  ║ camelCase  ║ camelCase    ║ camelCase  ║ lower_case ║
   ║ Pear Framework        ║ PascalCase  ║ camelCase  ║ camelCase    ║            ║            ║
   ║ Prado Framework       ║ PascalCase  ║ camelCase  ║ Pascal/camel ║            ║ lower_case ║
   ║ SimplePie RSS         ║ PascalCase  ║ lower_case ║ lower_case   ║ lower_case ║ lower_case ║
   ║ Symfony Framework     ║ PascalCase  ║ camelCase  ║ camelCase    ║ camelCase  ║ camelCase  ║
   ║ WordPress CMS         ║             ║            ║              ║ lower_case ║ lower_case ║
   ║ Zend Framework        ║ PascalCase  ║ camelCase  ║ camelCase    ║ camelCase  ║ camelCase  ║
   ╚═══════════════════════╩═════════════╩════════════╩══════════════╩════════════╩════════════╝
</pre>
