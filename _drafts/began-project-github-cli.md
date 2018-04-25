---
layout: post
title: "Began project 'github' CLI"
subtitle: "An utility for basic Github interaction right from the command line"
use_math: true
use_mermaid: true
categories: personal projects
abstract: |
  This is a multi line abstract entry that I use to validate the content on this page, and make it clear that this is a simple text. We need to test for **simple markdown** usage and *compliance*.
---

One thing that always bored me with GitHub when using the terminal was the lack of a CLI utility to interact with it. You always have to open a browser, head to the GitHub page and perform the action that you need to.<!--more-->

That's the main reason behind this small project. To provide a command line tool that directly interacts with the GitHub REST API to provide some services directly on the command line.

``` swift
let sampleConstant = 10.2
var sampleString = "Spell the magic"

func joinStrings() -> String {
    returnValue = "O valor da constante é: " + sampleConstant.toString()
    returnValue += "O valor da variavel é: " + sampleString
    return returnValue
}
```

{% pseudocode %}
PrefixTrieMatching(Text, Trie)
    symbol <- first letter of Text
    v <- root of Trie
    while forever
        if v is a leaf in Trie
            return the pattern spelled by the path from the root to v
        else if there is an edge (v, w) in Trie labeled by symbol
            symbol <- next letter of Text
            v <- w
        else
            output "no matches found"
            return

{% endpseudocode %}

{% highlight swift linenos %}
let sampleConstant = 10.2
var sampleString = "Spell the magic"

func joinStrings() -> String {
    returnValue = "O valor da constante é: " + sampleConstant.toString()
    returnValue += "O valor da variavel é: " + sampleString
    return returnValue
}
{% endhighlight %}

~~~
def what?
  42
end
~~~
{: .language-ruby}

```c
/* This is standard C code */

#include <stdio.h>

int main(int argc, char *argv[]) {
    double X = 1;
    return 0;
}
```

```c#
using System;

public class Hello {
    public static void Main(string[] args) {
        Console.WriteLine("Hello, world!");
    }
}
```


```python
# This is a python snippet

def __init__(self):
    self.data = []
```

```javascript
// This is a JavaScript one

var express = require('express'),
    https   = require('http'),
    fs      = require('fs');
```

```php
<html>
<?php
/* This is PHP in its essence */

$test = "Hello World!";
printf("<body>%s</body>\n", $test);
?>
</html>
```

```fortran
! This is the (not so) good and old FORTRAN

program hello
print *, 'This is a sample program...'
print *, 'Hello!'
end program hello
```

```objc
#import <Cocoa.h>

@interface AppDelegate ()
@property(strong) IBOutlet MASShortcutView *customShortcutView;
@property(strong) IBOutlet NSTextField *feedbackTextField;
@end

@implementation AppDelegate

- (void) awakeFromNib
{
    [super awakeFromNib];

    NSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];

    // Register default values to be used for the first app start
    [defaults registerDefaults:@{
        MASHardcodedShortcutEnabledKey : @YES,
        MASCustomShortcutEnabledKey : @YES,
        MASCustomShortcutKey : firstLaunchShortcutData
    }];
}
```

```swift
// This is the new Apple Swift language

extension String {
    func occurrenceOfString(aString: String) -> Int {
        // New extension members and/or behavior
        var occurrences: Int = 0
        var range: Range<String.Index>? = self.starIndex..<self.endIndex
        while range != nil {
            // Search in the current range
            range = self.rangeOfString(aString, options: NSStringCompareOptions.CaseInsensitiveSearch, range: range, locale: nil)
            if range != nil {
                // String was found, move the range
                range = range!.endIndex..<self.endIndex
                // Increment the number of occurrences
                occurrences++
            }
        }
        return occurrences
    }
}
```

```go
/* This is Go in it's simplest form */
package main

import "fmt"

func main() {
    fmt.Printf("Hello, world!\n")
}
```

```ruby
# This is a basic ruby gem ;-) 
def base
```


These are sample math formulas:

$$ F\left( x\right) = 2x+5-3 $$

$$ A_{(S-t)}^{(t-2)} = B $$

$$ \forall  x \in X, \quad \exists y \leq \epsilon $$

$$ \cos (2\theta) = \cos^2 \theta - \sin^2 \theta $$

$$ \lim_{x \to \infty} \exp(-x) = 0 $$

$$ \sum_{i=1}^{10} t_i $$

$$ \prod^{\infty}_{i=0} \frac{X_i}{\frac{i}{X}} $$

$$|\psi\rangle$$

This is a simple test of embbeded math inside a paragraph, like this $r^2$ power test. There are more issues with this, like this $s = \sqrt {\frac {N} {N + 1}}$ edge lenght of N simplex.

{% mermaid %}
sequenceDiagram
	Alice->>Bob: Hello, how are you?
	Bob->>Alice: I'm fine, thanks!
{% endmermaid %}

{% mermaid %}
graph LR
	A[Hard edge] -->|link text| B(Round edge)
	B --> C{Decision}
	C -->|One| D[Result 1]
	C -->|Two| E[Result 2]
{% endmermaid %}

{% mermaid %}
graph TD
	B["fa:fa-twitter for peace"]
	B --> C[fa:fa-ban forbidden]
	B --> D(fa:fa-spinner)
	B --> E(A fa:fa-camera-retro perhaps?)
{% endmermaid %}

{% mermaid %}
classDiagram
	Class01 <|-- AbstractClass : Realize
{% endmermaid %}