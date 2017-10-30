# Jibberish
Convert text or script into JavaScript gibberish

This is a JavaScript obfuscation program, inspired by [JSF*ck](http://jsfuck.com/) and [Hieroglyphy](http://patriciopalladino.com/files/hieroglyphy/).

It uses a bigger set of characters (21 chars), but it get the stuff done a lot quicker.
## How it works:
```(($,_,$$=+_,__)=>( ... ))({},'')```

This is an anonymous arrow function, which initializes ```$``` with an object and keep the global clean.

    $.$=!_+_, // 'true'
    $._=![]+_, // 'false'
    $.$$=__+_, // 'undefined'
    $.$_=$+_, // '[object Object]'
    $._$=!_/_+_, // 'Infinity'
  
These values are reached by simply casting certain types to string.

```$.__=$.$_[-~-~-~-~!_]+$.$_[++$$]+$.$$[$$++]+$._[++$$]+$.$[+_]+$.$[-~_]+$.$$[+_]+$.$_[-~++$$]+$.$[+_]+$.$_[-~_]+$.$[-~_]```

This spells 'constructor', which can give us the following:

    $.$$_=(+_)[$.__]+_, // 'function Number() { [native code] }'
    $.$_$=_[$.__]+_, // 'function String() { [native code] }'
    $.$__=/./[$.__]+_, // 'function RegExp() { [native code] }'
    __=(_=>_)[$.__] // Function
    
The last one is quite important, as it's equivalent to ```eval()```.

```$._$_=$.$[-~_]+$._[$$++]+$.$[+_]+$.$[-~!_]+$.$[-~_]+$.$$[-~_]``` spells 'return'.

And a bunch of stuff follows it to construct a ```toString()``` function that returns the letter ```'h'``` (yes, all for that one 'h').

Later, it uses the ```crypto``` keyword to get the string ```'[object Crypto]'```, which contain the letter 'C'.

Basically, the whole program first generates this function:

    function(...r) {
        return String.fromCharCode.apply(0, r);
    }
    
and then calls it with the unicode values of the normal string, which are all written in the form of obfuscated expressions.

I hope you understood all this gibberish explanation. Thanks for visiting.
