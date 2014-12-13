## Intro

**Deferred.JS** makes it **easy to handle asynchronous process** (like **AJAX**, etc).

Read **Motivation** section to know why you should move from JQuery Deferred to **Deferred.JS**.

**Deferred.JS** is a **alternative to JQuery Deferred objects**. (Acts same as JQuery Deferred).

To migrate from **JQuery Deferred** to **Deferred.JS** refer **Migration** section at the bottom.

## Code Example
------------------------------------------------------
..
// Simple asynchronous function written using Deferred object
function **after1Second**() {
	**var deferred = new dfrd.Deferred()**;
	setTimeout( function() { **deferred.resolve( 'after 1 second' );** }, 1000 );
	return **deferred**;
}
..
// Now easily handle asynchronous process
after1Second().**done**( function( message ) { console.log( 'This is printed ' + message ); } );
console.log( 'Called after1Second() method' );
..
-------------------------------------------------------

In the same way you can handle all asynchronous process. The most **frequently used asynchronous** process is **AJAX**.

## Doc

Methods are same as JQuery Deferred. So you can refer JQuery Deferred official doc.

Link: http://api.jquery.com/category/deferred-object/

**dfrd.version** --> Returns version of deferred object.
**dfrd.when( deferred1, deferred2, .... );** -->  Returns a deferred object which will be resolved on all the given diferred resolve.
**dfrd.addScopeTo( <scopeKey> );** --> Adds Deferred scope to given scope key.

## Migration

To migrate from JQuery Deferred object to this, just replace "$.Deferred" with "Dfrd.Deferred".
**Eg:**
..
var deferred = new **$.Deferred()**; --> var deferred = new **Dfrd.Deferred()**;
..

**Or**

Just add "**dfrd.addScopeTo( '$' );**".

## Motivation

**Plain Javascript** codes are **much faster** than any other library (Eg. **JQuery**, Dojo, Underscore, Prototype JS, Ext JS, YUI, Moo Tools).
Refer **Vanilla-JS** for **bechmark test** on various JS library. Link: http://vanilla-js.com/

But people find tough to handle asynchronous process without JQuery Deferred objects, so they will be forced to include entire JQuery library into their page (since JQuery Deferred is completely dependent on JQuery helper methods).

So we made a indepenent, efficient and light weignt library **dedicated only for handling asynchronous process**.

## Installation

Just include Deferred.js file in your page.
Eg:
..
<script src="/js/Deferred.js"></script>
..

And start using it.

## Contributors

Sundarasan Natarajan