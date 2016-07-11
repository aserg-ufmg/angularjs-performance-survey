# AngularJS Performance: A Survey Study

## Phase 1: Mapping Study 

#### [DOC1] Developer Guide: Scopes
* Access date: June-2015
* URL: https://docs.angularjs.org/guide/scope

> If a \mcode{\$watch} changes the value of the model, it will force additional digest cycle.

> Dirty checking the scope for property changes is a common operation in Angular and for this reason the dirty checking function must be efficient. Care should be taken that the dirty checking function does not do any DOM access, as DOM access is orders of magnitude slower than property access on JavaScript object.

> Dirty checking can be done with three strategies: By reference, by collection contents, and by value.


#### [DOC2] API Reference: mcode{$rootScope.Scope}
* Access date: June-2015
* URL: https://docs.angularjs.org/api/ng/type/$rootScope.Scope

> \mcode{\$destroy()} must be called on a scope when it is desired for the scope and its child scopes to be permanently detached from the parent and thus stop participating in model change detection and listener notification.

> Usually, you don't call \mcode{\$digest()} directly in controllers or in directives. Instead, you should call \mcode{\$apply()} (typically from within a directive), which will force a \mcode{\$digest()}.

#### [DOC3] API Reference: mcode{ngRepeat}
* Access date: June-2015
* URL: https://docs.angularjs.org/api/ng/directive/ngRepeat

> The \mcode{ngRepeat} directive instantiates a template once per item from a collection.

> Special properties are exposed on the local scope of each template instance: \mcode{\$index}, \mcode{\$first}, \mcode{\$middle}, \mcode{\$last}, \mcode{\$even} and \mcode{\$odd}. Creating aliases for these properties is possible with ngInit. This may be useful when, for instance, nesting ngRepeats.

> \mcode{ngRepeat} (as well as other ng directives) supports extending the range of the repeater by defining explicit start and end points by using \mcode{ng-repeat-start} and \mcode{ng-repeat-end}.


#### [BLOG1] Why You Should Not Use Angularjs
* Access date: June-2015 
* URL: https://medium.com/@mnemon1ck/why-you-should-not-use-angularjs-1df5ddf6fc99
* Author: Egor Koshelko
* Author Information: Senior Frontend Developer.

#### [BLOG2] AngularJS vs. Backbone.js vs. Ember.js
* Access date: June-2015
* URL: https://www.airpair.com/js/javascript-framework-comparison
* Author: Uri Shaked
* Author information: The author works for WatchDox, lectures at the Israel Institute of Technology, and organizes the Tel Aviv Google Developers Group.

#### [BLOG3] The Problem With Angular
* Access date: July-2015
* URL: http://www.quirksmode.org/blog/archives/2015/01/the_problem_wit.html
* Author: Peter-Paul Koch
* Author Information: Mobile platform strategist, consultant, and trainer.

#### [BLOG4] What's wrong with Angular
* Access date: July-2015
* URL: http://www.quirksmode.org/blog/archives/2015/01/the_problem_wit.html
* Author: Daniel Steigerwald
* Author Information: JavaScript Developer and Consultant. Member of the Google Developers Expert Program.

#### [BLOG5] Lessons learned from AngularJS
* Access date: July-2015
* URL: http://lhorie.github.io/mithril-blog/lessons-learned-from-angular.html
* Author Information: Developer in the project Mithril.

#### [BLOG6] AngularJS: The Bad Parts
* Access date: July-2015
* URL: http://larseidnes.com/2014/11/05/angularjs-the-bad-parts/
* Author: Lars Eidnes
* Author Information: Developer from Trondheim, Norway.

#### [BLOG7] Angular Bad Parts, Part 2: Performance
* Access date: July-2015
* URL: http://www.fse.guru/angular-bad-parts-part-2
* Author: Alexey Migutsky
* Author Information: Passionate software engineer, working with Scala, NodeJS and frontend technologies like Angular, ReactJS, HTML5, CSS.

#### [BLOG8] Optimizing AngularJS: 1200ms to 35ms
* Access date: June-2015
* URL: http://blog.scalyr.com/2013/10/angularjs-1200ms-to-35ms/
* Author: Steven Czerwinksi
* Author Information: Staff Software Engineer at Scalyr.

#### [BLOG9] Speeding Up AngularJS Apps With Simple Optimizations
* Access date: July-2015
* URL: http://www.binpress.com/tutorial/speeding-up-angular-js-with-simple-optimizations/135
* Author: Todd Motto
* Author Information: Director of Web Development at Mozio. He works with JavaScript and AngularJS.

#### [BLOG10] 11 Tips to Improve AngularJS Performance
* Access date: July-2015
* URL: http://www.alexkras.com/11-tips-to-improve-angularjs-performance/
* Author: Alex Kras
* Author Information: Software Engineer at Support.com.

#### [BLOG11] AngularJS: My Solution to the mcode{ng-repeat} Performance Problem
* Access date: July-2015
* URL: http://www.williambrownstreet.net/blog/2013/07/angularjs-my-solution-to-the-ng-repeat-performance-problem/
* Author: Thierry Nicola
* Author Information: Computer Scientist, working with Grails, AngularJS, BackboneJS, and ChaplinJS.

#### [BLOG12] AngularJS Performance in Large Applications
* Access date: July-2015
* URL: https://www.airpair.com/angularjs/posts/angularjs-performance-large-applications
* Author: Abraham Polishchuk
* Author Information: NodeJS/AngularJS engineer at Lanetix.

#### [BLOG13] Why The World Needed Another AngularJS Grid
* Access date: July-2015
* URL: http://www.angulargrid.com/why-the-world-needed-another-angularjs-grid/
* Author: Niall Crosby
* Author Information: The author has been writing software for 20 years, lately focusing on full stack Java/Javascript/AngularJS.

#### [BLOG14] Angular Non-trivial Performance Hints
* Access date: July-2015
* URL: http://codetunes.com/2015/angular-non-trivial-performance-hints/
* Author: Radek Markiewicz

#### [Q&A1] How Does Data Binding Work in AngularJS?
* Access date: July-2015
* URL: http://stackoverflow.com/questions/9682092/how-does-data-binding-work-in-angularjs/9693933#9693933
* Author: Misko Hevery
* Author Information: Contributor to AngularJS.

#### [Q&A2] How Do I Measure the Performance of my AngularJS App's Digest Cycle?
* Access date: June-2015
* URL: http://stackoverflow.com/q/23066422/5244036
* Author: Gil Birman

#### [Q&A3] AngularJS Scaling & Performance
* Access date: June-2015
* URL: http://stackoverflow.com/q/17656397/5244036

#### [Q&A4] How To Improve Performance Of mcode{ngRepeat} Over A Huge Dataset (Angular.js)?
* Access date: July-2015
* URL: http://stackoverflow.com/q/17348058/5244036

#### [Q&A5] How To Analyze Performance Benchmark In AngularJS Components?
* Access date: July-2015
* URL: http://stackoverflow.com/a/27400474/5244036}

#### [Q&A6] Ways To Improve AngularJS Performance Even With Large Number Of Dom Elements
* Access date: July-2015
* URL: http://stackoverflow.com/a/16128418/5244036}

#### [Q&A7] How To Speed Up An AngularJS Application?
* Access date: July-2015
* URL: http://stackoverflow.com/q/15643467/5244036

#### [Q&A8] Angular.js Performance Issues
* Access date: July-2015
* URL: http://stackoverflow.com/a/14486570/5244036
* Author: Ben Lesh

## Phase 2: Survey

https://github.com/aserg-ufmg/survey-angularjs-performance/blob/master/AngularJS-Performance-Form.pdf

