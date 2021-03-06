o.extend
====================

Object.prototype.extend() for node.js and the browser. ES5 compatible. ES5 incompatible enviroments are not supported(IE8 and less).
Has also a method Object.prototype.copyOwnProperties() which is much much simpler and faster.
#Usage
    
    var extended = Object.extend({b:1}, {a:2});
    //extended === {a:2, b:1}
    var extended = Object.copyOwnProperties({b:1}, {a:2});
    //extended === {a:2, b:1}
    
For usage examples, take a look at unit tests: https://github.com/capaj/o.extend/blob/master/test.js

Available via jspm/bower:
    
    jspm install github:capaj/o.extend
    bower install o.extend
  
or npm:

    npm install o.extend

##Why use this and not other implementations? 
Because this is only extend which can properly merge ES5 property descriptors, which means that if you merge object a with a setter and object b with getter on same property, result will have both getter and setter on that property.
So you don't lose any of your property descriptors when extending your objects.


Also you won't lose a setter when object which is extending base has a value. In that case the setter is not replaced, but instead it is called with the value as you would probably expect.

