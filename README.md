# Google Analytics Codox Theme

[![Clojars Project](https://img.shields.io/clojars/v/google-analytics-codox-theme.svg)](https://clojars.org/google-analytics-codox-theme)
[![Downloads](https://jarkeeper.com/rm-hull/google-analytics-codox-theme/downloads.svg)](https://jarkeeper.com/rm-hull/google-analytics-codox-theme)
[![Maintenance](https://img.shields.io/maintenance/yes/2016.svg?maxAge=2592000)]()

[codox](https://github.com/weavejester/codox) is a great tool for generating
API documentation from Clojure or ClojureScript source code.

With this codox theme, your `codox` documentation will automatically include
the inline javascript to track page hits using Google Analytics.

## Usage

You must use `codox` version **0.10.1** or above.

Add/blend the following to the `:dev` profile section in your _project.clj_:

```clojure
(defproject myproj 
  ...
  
  :profiles {
    :dev {
      :dependencies [
        [google-analytics-codox-theme "0.1.0"]]}})
```

Create or obtain your GA tracking code (this will usually be a value like
**UA-12345678-1**), and add/blend the following settings to the `:codox` map in
your project (obviously, substituting the _real_ tracking code):

```clojure
(defproject myproj 
  ...
  
  :codox {
    :themes [:default [:google-analytics {:tracking-code "UA-12345678-1"}]]})
```

Have a look at the [settings for a project already configured](https://github.com/rm-hull/infix/blob/master/project.clj) with this theme.

Run `lein codox` as normal and publish your newly generated html files: they
should now all include the relevant tracking code.

# License

## MIT License

Copyright (c) 2016 Richard Hull

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
