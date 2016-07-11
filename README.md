# AngularJS Performance: A Survey Study

## Phase 1: Mapping Study 

#### [DOC1] Developer Guide: Scopes
* Access date: June-2015
* URL: https://docs.angularjs.org/guide/scope

> If a `\$watch` changes the value of the model, it will force additional digest cycle.

> Dirty checking the scope for property changes is a common operation in Angular and for this reason the dirty checking function must be efficient. Care should be taken that the dirty checking function does not do any DOM access, as DOM access is orders of magnitude slower than property access on JavaScript object.

> Dirty checking can be done with three strategies: By reference, by collection contents, and by value.


#### [DOC2] API Reference: `$rootScope.Scope`
* Access date: June-2015
* URL: https://docs.angularjs.org/api/ng/type/$rootScope.Scope

> `\$destroy()` must be called on a scope when it is desired for the scope and its child scopes to be permanently detached from the parent and thus stop participating in model change detection and listener notification.

> Usually, you don't call `\$digest()` directly in controllers or in directives. Instead, you should call `\$apply()` (typically from within a directive), which will force a `\$digest()`.

#### [DOC3] API Reference: `ngRepeat`
* Access date: June-2015
* URL: https://docs.angularjs.org/api/ng/directive/ngRepeat

> The `ngRepeat` directive instantiates a template once per item from a collection.

> Special properties are exposed on the local scope of each template instance: `\$index`, `\$first`, `\$middle`, `\$last`, `\$even` and `\$odd`. Creating aliases for these properties is possible with ngInit. This may be useful when, for instance, nesting ngRepeats.

> `ngRepeat` (as well as other ng directives) supports extending the range of the repeater by defining explicit start and end points by using `ng-repeat-start` and `ng-repeat-end`.


#### [BLOG1] Why You Should Not Use Angularjs
* Access date: June-2015 
* URL: https://medium.com/@mnemon1ck/why-you-should-not-use-angularjs-1df5ddf6fc99
* Author: Egor Koshelko
* Author Information: Senior Frontend Developer.

> It's slow, and it is especially all turns bad on mobile platforms and when you write something complex.

> Angular even imposes restrictions on how rich UI you can write and this is not some ephemeral or distant limit you will never experience. It's only 2000 watchers, and if you develop more or less large applications, you will undoubtedly run into this limitation.

> When the user loads the page he may see \{\{expressions in brackets\`\`. For these purposes AngularJS introduces new directives: ngCloack, ngBind.

> (comment): That number is made up. Not true. Originally shared by Misko on StackOverflow. I'll get him to correct it. Complexity of an expression is often more important than the pure number of expressions. But in general when it comes to pure count we are talking about orders of magnitude bigger numbers than 2k (based on our benchmarks).

> (comment): That may be the reason why one way data-binding is now on 1.3. Fortunately, AngularJS evolves.

#### [BLOG2] AngularJS vs. Backbone.js vs. Ember.js
* Access date: June-2015
* URL: https://www.airpair.com/js/javascript-framework-comparison
* Author: Uri Shaked
* Author information: The author works for WatchDox, lectures at the Israel Institute of Technology, and organizes the Tel Aviv Google Developers Group.

> In general, for pages with a lot of interactive elements, Angular becomes really slow. A good rule of thumb is not to have more than 2,000 active bindings on the same page.

> Two-way data binding saves a lot of boilerplate code.

> The automatic Dirty Checking means that you don't have to access your model data with getters and setters — you can modify any property of an arbitrary scope object and angular will automatically detect the change and notify all the watchers for that property.

#### [BLOG3] The Problem With Angular
* Access date: July-2015
* URL: http://www.quirksmode.org/blog/archives/2015/01/the_problem_wit.html
* Author: Peter-Paul Koch
* Author Information: Mobile platform strategist, consultant, and trainer.

> What worries me is that this non-performant mode is Angular's default (talking about `ng-repeat` directive).

#### [BLOG4] What's wrong with Angular
* Access date: July-2015
* URL: http://www.quirksmode.org/blog/archives/2015/01/the_problem_wit.html
* Author: Daniel Steigerwald
* Author Information: JavaScript Developer and Consultant. Member of the Google Developers Expert Program.

> Angular is slow. And with dirty checking and HTML parsing always will be. Do I have to tell something about consequences for mobile web apps?

#### [BLOG5] Lessons learned from AngularJS
* Access date: July-2015
* URL: http://lhorie.github.io/mithril-blog/lessons-learned-from-angular.html
* Author Information: Developer in the project Mithril.

> Another problem related to Angular's re-implementation of scope is the steep performance degradation when things like grids grow past a modest size. Often things look ok with test data, but with production-level data volume, you are suddenly forced to discover about Angular internal concepts like watchers, dirty checking, apply cycles, etc, or you need to do massively time consuming audits of the code base in order to figure out the feasibility of adding the `ng-bindOnce` plugin, or maybe you need to completely rewrite a top-level `ng-repeat` to use the `ng-grid` plugin instead.

> It's extremely difficult to reason about Angular performance, and standard tools don't help very much.

#### [BLOG6] AngularJS: The Bad Parts
* Access date: July-2015
* URL: http://larseidnes.com/2014/11/05/angularjs-the-bad-parts/
* Author: Lars Eidnes
* Author Information: Developer from Trondheim, Norway.

> The digest loop: It scans through everything that has such a binding, and sees if it has changed by comparing its value to a stored copy of its value. It then scans through everything looking for changes again. This keeps going until no more changes are detected.

> Changing anything in the application becomes an operation that triggers hundreds or thousands of functions looking for changes.

> This is a fundamental part of what Angular is, and it puts a hard limit on the size of the UI you can build in Angular while remaining performant.

> It's not hard to end up with more than 2000 bindings.

> On mobiles the performance was dreadful.

> There are ways to make bindings happen only once, and with Angular version 1.3 these are included by default. It nevertheless requires ditching what is perhaps the most fundamental abstraction in Angular.

#### [BLOG7] Angular Bad Parts, Part 2: Performance
* Access date: July-2015
* URL: http://www.fse.guru/angular-bad-parts-part-2
* Author: Alexey Migutsky
* Author Information: Passionate software engineer, working with Scala, NodeJS and frontend technologies like Angular, ReactJS, HTML5, CSS.

> Do you know that each time you call `\$scope.\$apply()` you actually call `\$rootScope.\$apply()` and this call updates all scopes and run all your watches?.

> Moreover, `\$rootScope.\$apply()` is called each time when: 
>*`\$timeout` handler is invoked (almost all debounce services are broken by design)
>*`\$http` receives a response (yeah, if you have a polling implemented on `\$http`...)
* Any DOM handler is called (have you throttled your `ng-mouseovers`? They actually invoke ALL your `\$watches`, and built-in digest phasing does not really help)

#### [BLOG8] Optimizing AngularJS: 1200ms to 35ms
* Access date: June-2015
* URL: http://blog.scalyr.com/2013/10/angularjs-1200ms-to-35ms/
* Author: Steven Czerwinksi
* Author Information: Staff Software Engineer at Scalyr.

> In our early tests, we found that advancing to the next log page could take several agonizing seconds of JavaScript execution. Worse, unrelated actions (such as clicking on a navigation dropdown) now had noticeable lag.

> We created a directive that “hides” the change watchers of its children. To accomplish this, we had to slightly break the AngularJS abstraction layer.

> A straightforward AngularJS implementation of the log view took 1.2 seconds to advance to the next page, but with some careful optimizations we were able to reduce that to 35 milliseconds. We had to break few rules to implement them.

> (comment): AngularJS 1.3 introduces one-time binding to reduce watching and digest loops which is relevant to this.

> (comment): Yes, with the current implementation's approach, if the AngularJS team changed the `\$scope.\$watch` implementation to use a different non-public variable that we depend on, our change would break and we would have to fix it..


#### [BLOG9] Speeding Up AngularJS Apps With Simple Optimizations
* Access date: July-2015
* URL: http://www.binpress.com/tutorial/speeding-up-angular-js-with-simple-optimizations/135
* Author: Todd Motto
* Author Information: Director of Web Development at Mozio. He works with JavaScript and AngularJS.

> AngularJS dropped a really interesting feature recently in the beta version of 1.3.0: the ability to render data once and let it persist without being affected by future Model updates.

> When `\$scope.\$apply()` is called it runs `\$rootScope.\$digest()`. This is what actually kicks off the internal digest cycle.

> Instead of `\$scope.\$apply`, we could turn to `\$scope.\$digest`, which runs the exact same digest loop, but is executed from the current scope downwards through its children. The only caveat to this approach is that if you're dependent on two-way binding between Objects from the parent scope, the parent scope won't be updated until the next `\$rootScope` full digest cycle.

> Avoid `ng-repeat` where possible. The `ng-repeat` directive is most likely the worst offender for performance concerns.

> Instead of rendering a global navigation using `ng-repeat`, we could create our own navigation using the `\$interpolate` provider to render our template against an Object and convert it into DOM nodes.

> Another offender that will increase `\$\$watcher` counts are the core Angular directives such as `ng-show` and `ng-hide`. Although these might not immediately increase watcher counts dramatically, they can easily stack up in the hundreds inside an `ng-repeat`.

> Angular also provides us with Directives such as `ng-mouseenter`, these can be more costly too as they're not only binding an event listener, they become a part of the digest cycle adding to the application weight.

> Limit DOM filters. Angular includes a `\$filter` provider, which you can use to run filters in your JavaScript before parsing into the DOM.

#### [BLOG10] 11 Tips to Improve AngularJS Performance
* Access date: July-2015
* URL: http://www.alexkras.com/11-tips-to-improve-angularjs-performance/
* Author: Alex Kras
* Author Information: Software Engineer at Support.com.

> In Angular it is fairly easy to add so many watchers that your app will slow down to a crawl.

> Angular 1.3 added `::` notation to allow one time binding. Angular will wait for a value to stabilize after its first series of digest cycles; after that, Angular will remove the watcher forgetting about that binding. If you are on pre 1.3 version of Angular you can use this library to achieve similar results.

> Use `\$watchCollection` instead of `$watch` (with a 3rd parameter).

> If you know there is going to be a lot of changes coming from an `ng-model`, you can de-bounce the input. For example if you have a search input like Google, you can de-bounce it by setting the following `ng-model` option: `ng-model-options="{ debounce: 250 `"`. This will ensure that the digest cycle due to the changes in this input model will get triggered no more than once per 250ms.

> Use `ng-if` instead of `ng-show` (but confirm that `ng-if` is actually better for your use case).

> Console.time is a great API, and I found it particularly helpful when debugging issues with Angular performance.

> Use native JavaScript or Lodash for slow functions: In my tests I got a significant performance boost by simply re-writing some of the basic logic with lodash, instead of relying on built-in Angular methods (which have to account for much more generic use cases).

> Use Chrome Timeline and Profiler to identify performance bottlenecks: I like to think of myself as a Chrome Dev Tools power user. But it’s not often that I get a to use the Timeline and Profiler views. In this project, both were extremely helpful.

> I just found yesterday a less known easy way to speed up angular : turn off angular’s debug features!

#### [BLOG11] AngularJS: My Solution to the mcode{ng-repeat` Performance Problem
* Access date: July-2015
* URL: http://www.williambrownstreet.net/blog/2013/07/angularjs-my-solution-to-the-ng-repeat-performance-problem/
* Author: Thierry Nicola
* Author Information: Computer Scientist, working with Grails, AngularJS, BackboneJS, and ChaplinJS.

> After some testing, the response times were very satisfying, however the application was blocking for 500-700ms after each refresh of the view. Quickly I stumble upon the problem: `ng-repeat`.

> I was expecting this bad performance due to the internal working of AngularJS.

> For `ng-repeat` you often want the items to be rendered and then forget about them as they are not updated from the client side. No two way binding required.

> Bindonce (plugin or third-party module) allows to create a template to render that uses jQuery to render the HTML, so no two-way binding. This solved the problem of the slow rendering, but created another one namely that scrolling now had bad performance (on mobile scrolling was not controllable).

> Virtual Scrolling just renders the visible elements and removes invisible elements from the DOM.

> Final solution: Upgrade to AngularJS 1.1.5 and use limitTo together with Infinite scrolling.

> I slightly adapted the Infinite Scroll directive to make scrolling within a container possible that does not have height 100\% of window.

> The limitTo with Infinite Scrolling plays very neat together with the Track By feature for `ng-repeat`.

#### [BLOG12] AngularJS Performance in Large Applications
* Access date: July-2015
* URL: https://www.airpair.com/angularjs/posts/angularjs-performance-large-applications
* Author: Abraham Polishchuk
* Author Information: NodeJS/AngularJS engineer at Lanetix.

> It is important to understand what causes an AngularJS application to slow down.

> A fantastic tool for benchmarking one's code is jsPerf. The Chrome Dev Tools have a fantastic JavaScript profiler.

> There are several things to be said about performant Javascript that are not necessarily limited to Angular.

> Now that we have discussed JavaScript performance, it is important to understand a few key Angular concepts that are somewhat under the hood.

> Of particular importance to writing Angular JS applications in general and performance in particular is the digest cycle. Effectively, every scope stores an array of functions `$\watchers`.

> When any value in scope changes, all watchers in the `$$watchers` array will fire, and if any of them modify a watched value, they will all fire again.

> We should think through our data model and attempt to limit the complexity of our objects. Use a custom serializer to only return the subset of keys that your Angular application absolutely must have.

> Never watch a function result directly. This function will run on every digest cycle.

> Every time `\$watch` is called on a scope value, or a value is bound from the DOM with interpolation, an `ng-repeat`, an `ng-switch`, and `ng-if`, or any other DOM attribute/element, a function gets added to the `$$watchers` array of the innermost scope.

> If non-Angular code is run through `\$scope.\$apply()`, this will immediately kickstart the digest cycle.

> Design with Angular in mind.

> Angular provides the ability to watch entire objects by passing a third, optional true parameter to `\$scope.\$watch`. This is a terrible idea.

> `ng-repeat` does some pretty heavy DOM manipulation (not to mention polluting `$$watchers`). Keep any lists of rendered data small whether through pagination or infinite scroll.

> Avoid using filters if at all possible. They are run twice per digest cycle and do not actually remove any part of the collection from memory.

> It is also important to avoid a global list refresh when using `ng-repeat`. Doing something like `\$scope.listBoundToNgRepeat = serverFetch()` will cause a complete recalculation of the entire list, causing transcludes to run and watchers to fire for every individual element. This is a very expensive proposition. There are two ways around this. One is to maintain two collections and `ng-repeat` over the filtered set. The other is to use \emph{track by` to specify your own key.

> Track by approach only works when a field on the repeated object can be guaranteed to be unique in the set.

> `ng-hide` and `ng-show` simply toggle the CSS display property: Any scopes will exist, all `\$\$watchers` will fire, etc. `ng-if` and `ng-switch` actually remove or add the DOM completely. Unfortunately this results in a case by case judgment call.

> A common source of slow Angular applications is incorrect use of `ng-hide` and `ng-show` over `ng-if` or `ng-switch`. The distinction is nontrivial, and the importance can not be overstated in the context of performance.

> The problem arises in the fact that `\$scope.\$apply` starts at `\$rootScope` and walks the entire scope chain causing every scope to fire every watcher.

> In general, `\$scope.\$watch` is indicative of bad architecture.

> `\$on`, `\$broadcast` , and `\$emit`, like `\$watch`, are slow as events (potentially) have to walk your entire scope hierarchy.

> `evalAsync` can greatly improve your page's performance.

> By creating a new scope with Isolate Scope or Transclusion, we are creating a new object to track, adding new watchers, and therefore slowing down our application.

> Angular provides many pre-rolled DOM event directives. `ng-click`, `ng-mouseenter`, `ng-mouseleave`, etc. All of these call `\$scope.\$apply()` every time the event occurs. A much more efficient approach is to bind directly with addEventListener, and then use `\$scope.\$digest` as necessary.

#### [BLOG13] Why The World Needed Another AngularJS Grid
* Access date: July-2015
* URL: http://www.angulargrid.com/why-the-world-needed-another-angularjs-grid/
* Author: Niall Crosby
* Author Information: The author has been writing software for 20 years, lately focusing on full stack Java/Javascript/AngularJS.

> You see, Angular JS is great for form based applications, where you don't have hundreds of bound values laid out in a grid and scrolling.

> The extra logic that AngularJS puts in behind the scenes doesn't work in your favor when building something like a complex grid.

#### [BLOG14] Angular Non-trivial Performance Hints
* Access date: July-2015
* URL: http://codetunes.com/2015/angular-non-trivial-performance-hints/
* Author: Radek Markiewicz

> Avoid complicated watcher's evaluation.

> There is no way to think about the higher level of Angular performance without understanding a few things:
>* How digest cycle works in general
>* Difference between `\$scope.\$apply()` and `\$scope.\$digest()`
>* List of Angular core features triggering digest cycle

#### [Q&A1] How Does Data Binding Work in AngularJS?
* Access date: July-2015
* URL: http://stackoverflow.com/questions/9682092/how-does-data-binding-work-in-angularjs/9693933#9693933
* Author: Misko Hevery
* Author Information: Contributor to AngularJS.

> You can't really show more than about 2000 pieces of information to a human on a single page. Anything more than that is really bad UI, and humans can't process this anyway.

> Unfortunately it is way too easy to add a slow comparison into AngularJS, so it is easy to build slow applications when you don't know what you are doing.

#### [Q&A2] How Do I Measure the Performance of my AngularJS App's Digest Cycle?
* Access date: June-2015
* URL: http://stackoverflow.com/q/23066422/5244036
* Author: Gil Birman
* 
> What is a simple way to measure the duration of the angularjs digest cycle? 

#### [Q&A3] AngularJS Scaling & Performance
* Access date: June-2015
* URL: http://stackoverflow.com/q/17656397/5244036

> You need to create custom directives in order to curb the performance issues with angular. Unlike ember angular comes with all the bells and whistles turned on and it's up to you to tone it down.

#### [Q&A4] How To Improve Performance Of mcode{ngRepeat` Over A Huge Dataset (Angular.js)?
* Access date: July-2015
* URL: http://stackoverflow.com/q/17348058/5244036

> Most straightforward approach (fetch data, put it into `\$scope`, let `ng-repeat=""` do its job) works fine, but it freezes the browser for about half of a minute when it starts inserting nodes into DOM.

#### [Q&A5] How To Analyze Performance Benchmark In AngularJS Components?
* Access date: July-2015
* URL: http://stackoverflow.com/a/27400474/5244036`

> The `\$apply` function itself is relatively light (you can inspect it in the angular source). It is the process of evaluating watchers and comparing values (dirty-checking) during a `\$digest` that can get expensive.


#### [Q&A6] Ways To Improve AngularJS Performance Even With Large Number Of Dom Elements
* Access date: July-2015
* URL: http://stackoverflow.com/a/16128418/5244036`

> I think that the best way to solve performance issues is to avoid using high level abstractions (AngularJS `ng-repeat` with all corresponding background magic) in such situations. AngularJS is not a silver bullet and it's perfectly working with low level libraries.

#### [Q&A7] How To Speed Up An AngularJS Application?
* Access date: July-2015
* URL: http://stackoverflow.com/q/15643467/5244036

> The thing you can do that will speed up your Angular app the most is to reduce those bindings where you can. One way to do this would be to create a directive that built out the table for you with DOM manipulation rather than using `ng-repeat`s.

#### [Q&A8] Angular.js Performance Issues
* Access date: July-2015
* URL: http://stackoverflow.com/a/14486570/5244036
* Author: Ben Lesh

> Every `ngRepeat` you set up, sets up a watch. Every `{{binding}}` or `ngModel` you do inside of that repeat, sets up another watch, and so on. Each of those creates function and object instances, and also needs to be processed on every `\$digest`. So, if your running into performance issues, you may need to implement a custom directive that writes out your data without setting up those superfluous watches, so you're a little more performant.

## Phase 2: Survey

https://github.com/aserg-ufmg/survey-angularjs-performance/blob/master/AngularJS-Performance-Form.pdf

