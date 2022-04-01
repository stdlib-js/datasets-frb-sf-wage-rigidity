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

# Wage Rates

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Wage rates][@frbsf:wagerigidity] for U.S. workers that have not changed jobs within the year.

<section class="intro">

</section>

<!-- /.intro -->



<section class="usage">

## Usage

To use in Observable,

```javascript
wages = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/datasets-frb-sf-wage-rigidity@umd/bundle.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/datasets-frb-sf-wage-rigidity@umd/bundle.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.wages;
})();
</script>
```

#### wages()

Returns [wage rates][@frbsf:wagerigidity] for U.S. workers that have not changed jobs within the year.

```javascript
var data = wages();
// returns [{...},{...},...]
```

Each `array` element has the following fields:

-   **date**: collection date (month/day/year; e.g., `01/01/1980`).
-   **all_workers**: wage rates for hourly and non-hourly workers.
-   **hourly_workers**: wage rates for hourly workers.
-   **non_hourly_workers**: wage rates for non-hourly workers.
-   **less_than_high_school**: wage rates for workers with less than a high school education.
-   **high_school**: wage rates for workers with a high school education.
-   **some_college**: wage rates for workers with some college education.
-   **college**: wage rates for workers with a college education.
-   **construction**: wage rates for workers in the construction industry.
-   **finance**: wage rates for workers in the finance industry.
-   **manufacturing**: wage rates for workers in the manufacturing industry.

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/plot-sparklines-unicode-tristate@umd/bundle.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/datasets-frb-sf-wage-rigidity@umd/bundle.js"></script>
<script type="text/javascript">
(function () {

var chart;
var opts;
var data;
var v1;
var v2;
var d;
var i;

data = wages();
d = new Array( data.length );
v1 = data[ 0 ].all_workers;
for ( i = 1; i < data.length; i++ ) {
    v2 = data[ i ].all_workers;
    if ( v2 === null ) {
        d[ i ] = NaN;
    } else if ( v2 < v1 ) {
        d[ i ] = -1;
    } else if ( v2 > v1 ) {
        d[ i ] = 1;
    } else {
        d[ i ] = 0;
    }
    v1 = v2;
}

opts = {
    'data': d
};
chart = new Chart( opts );

console.log( chart.render() );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->



<!-- <license> -->

* * *

## License

The data files (databases) are licensed under an [Open Data Commons Attribution 1.0 License][odc-by-1.0] and their contents are licensed under a [Creative Commons Attribution 4.0 International Public License][cc-by-4.0]. The original dataset is attributed to the [Federal Reserve Bank of San Francisco][@frbsf:wagerigidity]. The software is licensed under [Apache License, Version 2.0][apache-license].

<!-- </license> -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

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

## Copyright

Copyright &copy; 2016-2022. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/datasets-frb-sf-wage-rigidity.svg
[npm-url]: https://npmjs.org/package/@stdlib/datasets-frb-sf-wage-rigidity

[test-image]: https://github.com/stdlib-js/datasets-frb-sf-wage-rigidity/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/datasets-frb-sf-wage-rigidity/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/datasets-frb-sf-wage-rigidity/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/datasets-frb-sf-wage-rigidity?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/datasets-frb-sf-wage-rigidity.svg
[dependencies-url]: https://david-dm.org/stdlib-js/datasets-frb-sf-wage-rigidity/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/datasets-frb-sf-wage-rigidity/tree/deno
[umd-url]: https://github.com/stdlib-js/datasets-frb-sf-wage-rigidity/tree/umd
[esm-url]: https://github.com/stdlib-js/datasets-frb-sf-wage-rigidity/tree/esm

[@frbsf:wagerigidity]: http://www.frbsf.org/economic-research/indicators-data/nominal-wage-rigidity/

[csv]: https://tools.ietf.org/html/rfc4180

[ndjson]: http://specs.frictionlessdata.io/ndjson/

[odc-by-1.0]: http://opendatacommons.org/licenses/by/1.0/

[cc-by-4.0]: http://creativecommons.org/licenses/by/4.0/

[apache-license]: https://www.apache.org/licenses/LICENSE-2.0

</section>

<!-- /.links -->
