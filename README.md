<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# Write-Only Accessor

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Define][@stdlib/utils/define-property] a **write-only** accessor.



<section class="usage">

## Usage

To use in Observable,

```javascript
setWriteOnlyAccessor = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/utils-define-write-only-accessor@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var setWriteOnlyAccessor = require( 'path/to/vendor/umd/utils-define-write-only-accessor/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/utils-define-write-only-accessor@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.setWriteOnlyAccessor;
})();
</script>
```

#### setWriteOnlyAccessor( obj, prop, setter )

[Defines][@stdlib/utils/define-property] a **write-only** accessor.

```javascript
var obj = {};
var val = '';

function setter( v ) {
    val = v;
}

setWriteOnlyAccessor( obj, 'foo', setter );

obj.foo = 'boop';

var bool = ( val === 'boop' );
// returns true
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Write-only accessors are **enumerable** and **non-configurable**.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/utils-define-write-only-accessor@umd/browser.js"></script>
<script type="text/javascript">
(function () {

function Foo( secret ) {
    if ( !(this instanceof Foo) ) {
        return new Foo( secret );
    }
    setWriteOnlyAccessor( this, 'secret', setter );
    return this;

    function setter( v ) {
        secret = v;
    }
}

var foo = new Foo( 'beep' );

foo.secret = 'boop';

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/utils/define-read-only-property`][@stdlib/utils/define-read-only-property]</span><span class="delimiter">: </span><span class="description">define a read-only property.</span>
-   <span class="package-name">[`@stdlib/utils/define-read-only-accessor`][@stdlib/utils/define-read-only-accessor]</span><span class="delimiter">: </span><span class="description">define a read-only accessor.</span>
-   <span class="package-name">[`@stdlib/utils/define-read-write-accessor`][@stdlib/utils/define-read-write-accessor]</span><span class="delimiter">: </span><span class="description">define a read-write accessor.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2022. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/utils-define-write-only-accessor.svg
[npm-url]: https://npmjs.org/package/@stdlib/utils-define-write-only-accessor

[test-image]: https://github.com/stdlib-js/utils-define-write-only-accessor/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/utils-define-write-only-accessor/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/utils-define-write-only-accessor/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/utils-define-write-only-accessor?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/utils-define-write-only-accessor.svg
[dependencies-url]: https://david-dm.org/stdlib-js/utils-define-write-only-accessor/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/utils-define-write-only-accessor/tree/deno
[umd-url]: https://github.com/stdlib-js/utils-define-write-only-accessor/tree/umd
[esm-url]: https://github.com/stdlib-js/utils-define-write-only-accessor/tree/esm
[branches-url]: https://github.com/stdlib-js/utils-define-write-only-accessor/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/utils-define-write-only-accessor/main/LICENSE

[@stdlib/utils/define-property]: https://github.com/stdlib-js/utils-define-property/tree/umd

<!-- <related-links> -->

[@stdlib/utils/define-read-only-property]: https://github.com/stdlib-js/utils-define-read-only-property/tree/umd

[@stdlib/utils/define-read-only-accessor]: https://github.com/stdlib-js/utils-define-read-only-accessor/tree/umd

[@stdlib/utils/define-read-write-accessor]: https://github.com/stdlib-js/utils-define-read-write-accessor/tree/umd

<!-- </related-links> -->

</section>

<!-- /.links -->
