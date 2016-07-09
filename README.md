# AngularJS Performance: A Survey Study

List of documents collected and reviewed in the initial mapping study.

#### [DOC1] Developer Guide: Unit Testing
* Access date: September-2015
* URL: https://docs.angularjs.org/guide/unit-testing

> One of the most useful parts of ngMock is \$httpBackend, which lets us mock XHR requests in tests, and return sample data instead.

> Angular is written with testability in mind, but it still requires that you do the right thing. We tried to make the right thing easy, but if you ignore these guidelines you may end up with an untestable application.

> Angular also provides the ngMock module, which provides mocking for your tests. This is used to inject and mock Angular services within unit tests. In addition, it is able to extend other modules so they are synchronous. Having tests synchronous keeps them much cleaner and easier to work with.

#### [DOC2] API Reference: `$compile`
* Access date:` September-2015
* URL: https://docs.angularjs.org/api/ng/service/$compile

> There are many different options for a directive.

> The isolate scope object hash defines a set of local scope properties derived from attributes on the directive's element. These local properties are useful for aliasing values for templates. The keys in the object hash map to the name of the property on the isolate scope; the values define how the property is bound to the parent scope, via matching attributes on the directive's element

#### [BLOG1] Choosing a JavaScript MVC Framework
* Access date: June-2015` 
* URL: http://www.funnyant.com/choosing-javascript-mvc-framework/
* Author: Craig McKeachie
* Author information: Microsoft Certified Solutions Developer.

> With Angular and Ember you usually have to live with the choices made by the authors of the frameworks, which may or may not suit your project needs and personal style.

> It's important to understand how big a download of each of these frameworks is and what you are getting for that extra weight in your application.

#### [BLOG2] AngularJS vs. Backbone.js vs. Ember.js
* Access date: August-2015
* URL: https://www.airpair.com/js/javascript-framework-comparison
* Author: Uri Shaked
* Author information: The author works for WatchDox, lectures at the Israel Institute of Technology, and organizes the Tel Aviv Google Developers Group.

> Angular helps you categorize your application building blocks into several types: Controllers, Directives, Factories, Filters, Services and Views (templates).

> The Digest Cycle of angular, which takes care of the Magical dirty checking, has the tendency to surprise developers. It is easy to forget to call `\$digest()` when running in non-Angular context.

> Putting logic inside the templates makes it harder to test, as it becomes impossible to test it in isolation.

> Mistakes such as misspelling a directive name or calling an undefined scope function are silently ignored and can be challenging to find.

> Failing to understand scope inheritance causes many cases of frustrated developers.

> Wrapping your head around all the concepts such as compiling function, pre/post linking functions, the different scope kinds (transclusion / isolate / child scope) and all the other configuration settings for directives takes some time to master.

> Promises play a main role in the Angular cast.

#### [BLOG3] Unit Testing AngularJS Directives With External Templates
* Access date: September-2015 
* URL: http://www.bluesphereinc.com/blog/unit-testing-angularjs-directives
* Author: Chris Hooker
* Author information: The author is a graduate of MIT, and has over 15 years of software development experience.

> I hate including HTML inline as a string in Javascript, so I definitely wanted to use `templateUrl`. This was all fine and good, and I got my directive up and running. Then I decided it was time to unit test it. That's where the real fun began.

> I discovered that while getting some simple unit tests running wasn't too hard using just Jasmine, unit testing my `templateUrl` directive was no simple matter.

> The problem with using `templateUrl` is that Angular uses an HTTP request to go get the file. However, in a unit-testing environment, you don't have the full web server environment and can't actually make the HTTP request. So, you'll get an error when you try to test the directive.

> You want to pre-process your HTML template and convert in into Javascript, which can be testing without any need for HTTP requests.

#### [BLOG4] What's wrong with Angular
* Access date: September-2015
* URL: http://www.quirksmode.org/blog/archives/2015/01/the_problem_wit.html
* Author: Daniel Steigerwald
* Author information: JavaScript Developer and Consultant. Member of the Google Developers Expert Program.

> Dirty checking, accessors (Ember and Backbone), `Object.observe` and all that stuff. Wrong! It's slow and brittle and it will consume mobile battery like hungry dog, for no reason.

> Angular is HTML parser. I really don't want to debug any string based parser instead of my code.

#### [BLOG5] Optimizing AngularJS: 1200ms to 35ms
* Access date: August-2015
* URL: http://blog.scalyr.com/2013/10/angularjs-1200ms-to-35ms/
* Author: Steven Czerwinksi
* Author information: Staff Software Engineer at Scalyr.

> This shows the power of AngularJS for encapsulation and separation of concerns.

#### [BLOG6] Speeding Up AngularJS Apps With Simple Optimizations
* Access date: August-2015
* URL: http://www.binpress.com/tutorial/speeding-up-angular-js-with- simple-optimizations/135
* Author: Todd Motto
* Author information: Director of Web Development at Mozio. He works with JavaScript and AngularJS.

> You'll get an error thrown from Angular if you're calling `\$scope.\$apply` in the wrong place, usually too high up the call stack.

#### [BLOG7] AngularJS: My Solution to the mcodeng-repeat Performance Problem
* Access date: July-2015
* URL: http://www.williambrownstreet.net/blog/2013/07/angularjs-my-solution-to-the-ng-repeat-performance-problem/
* Author: Thierry Nicola
* Author information: Computer Scientist, working with Grails, AngularJS, BackboneJS, and ChaplinJS.

> I started with BackboneJS as frontend MVC, but soon switch to AngularJS because of the concept AngularJS adds to HTML.

> AngularJS offers just the right structure for code organization. After some effort to learn to use directives and services, AngularJS forces me to get my code clean.

#### [BLOG8] AngularJS Performance in Large Applications
* Access date: August-2015
* URL: https://www.airpair.com/angularjs/posts/angularjs-performance-large-applications
* Author: Abraham Polishchuk
* Author information: NodeJS/AngularJS engineer at Lanetix.

> Isolate Scope and Transclusion are some of the most exciting things about Angular. They allow the building of reusable, encapsulated components, they are syntactically and conceptually elegant and a core part of what makes Angular Angular.

#### [BLOG9] Why You Should Not Use Angularjs
* Access date: June-2015
* URL: https://medium.com/@mnemon1ck/why-you-should-not-use-angularjs- 1df5ddf6fc99
* Author: Egor Koshelko
* Author information: Fullstack NodeJS Developer.

> Errors in bindings don't fire at all.

> You can't put a breakpoint inside \{\{ this expression \`\`.

> When you write in AngularJS you put your logic into your HTML (`ng-repeat`, `ng-show`, `ng-class`, `ng-model`, `ng-init`, `ng-click`, `ng-switch`, `ng-if`). Existence of such logic is not as bad as the fact that it is impossible to test this logic with unit tests, this logic can't be debugged and errors don't fire from markup (but this code contains very important logic).

> Errors that occurred in JavaScript are caught by the internal angular interceptor, and interpreted by browser as caught errors (everything that happens in AngularJS, stays in AngularJS).

>  (comment) The null reference exceptions (in templates (HTML)) are swallowed in order to not break the first renders working properly.

> It's unclear why it was necessary to introduce several ways to do the same thing.

> It is without a doubt the most common error that absolutely every AngularJS developer faces (Scope inheritance).

> There is no logical reason to separate logic for 3 methods (`compile`, `link`, `controller`), all this can be easily implemented in a single method.

> Even in order to integrate some code in the angular world, for example some jQuery plugin, you need to wrap it in a directive.

> Since server side rendering adds logic into your HTML and AngularJS writes logic in HTML, there is no clear separation of concerns and as a result you get spaghetti code.

> The only good thing that AngularJS has is that it forces developers to break their logic into modules, and code becomes more granulated.


#### [BLOG10] AngularJS Critique
* Access date: October-2015
* URL: http://tutorials.jenkov.com/angularjs/critique.html
* Author: Jakob Jenkov
* Author information: Founder and CEO at Jenkov Aps.

> Before AngularJS it was best practice to keep function calls out of the HTML. For instance, you should not use the `onclick` event attributes on HTML elements, but rather attach event listeners via JavaScript. Somehow that was forgotten with AngularJS, and now we are back to embedding JavaScript function calls in the HTML.

> In order to teach HTML new tricks you end up with HTML full of non-HTML elements and attributes.

> We are back to embedding JavaScript function calls in the HTML.

#### [BLOG11] Debugging AngularJS
* Access date: October-2015
* URL: https://www.ng-book.com/p/Debugging-AngularJS/
* Author: Ari Lerner
* Author information: Developer with more than 20 years of experience, and co-founder of Fullstack.io. The author has been using AngularJS for a long time and is a recognized expert in the field.

> Angular Batarang is a Chrome extension developed by the Angular team at Google that integrates very nicely as a debugging tool for Angular apps.

#### [BLOG12] A Guide To Transclusion in AngularJS
* Access date: October-2015
* URL: http://teropa.info/blog/2015/06/09/transclusion.html
* Author: Tero Parviainen

> Based on what I've heard, I'm not alone in this. Transclusion is one of those things people often mention when they talk about their difficulties with Angular.

> I think the bigger problems (with transclusion) are tangential:
>* The API is tricky, with its higher-order functions and magic arguments.
>* Parts of the API are deprecated, and it can be hard to figure out which parts.
>* The documentation uses lots of big words (a transclude linking function pre-bound to the correct transclusion scope).
>* There are actually two separate features provided by the same API: Regular transclusion and element transclusion.

#### [BLOG13] An Intervention: Why AngularJS is Worse Than a New ASP.NET WebForms
* Access date: October-2015
* URL: https://medium.com/@benastontweet/an-intervention-4535d835e836
* Author: Ben Aston
* Author information: Consultant developer specializing in web applications.

> AngularJS brings with it a domain specific language: transclusion, scope, directives, modules, factories and services.

> You could probably sum up AngularJS with this single word: it makes the inclusion of DOM fragments in your page sound novel and complicated.

#### [BLOG14] Scope Creep, a Deep Dive Into Angular's Scope
* Access date: October-2015
* URL: http://jonathancreamer.com/working-with-all-the-different-kinds-of-scopes-in-angular/
* Author: Jonathan Creamer
* Author information: JavaScript, Ruby, C#, Node, Rails, .NET MVC, MS MVP, Telerik Developer Expert, and IEuserAgent.

> Getting used to the concept of scope in Angular is among the more difficult concepts to fully grok when first being introduced to the magical land of Angular.

> Because of the fact that the scopes do inherit from other scopes, if you create a primitive value (string, number, boolean) on a parent scope, the child scope will have an be able to manipulate the value.

#### [BLOG15] Adding Clarity to Scope Inheritance in Angular
* Access date: October-2015
* URL: http://jonathancreamer.com/adding-clarity-to-scope-inheritance-in-angular/
* Author: Jonathan Creamer
* Author information: JavaScript, Ruby, C#, Node, Rails, .NET MVC. MS MVP, Telerik Developer Expert, and IEuserAgent.

> The fact is prototypical inheritance in JavaScript presents confusion to a lot of folks out there. In terms of Angular.js that may explain why the concept of `\$scope` is difficult to grok.

#### [BLOG16] Mastering AngularJS directives
* Access date: October-2015
* URL: http://code.tutsplus.com/tutorials/mastering-angularjs-directives--cms-22511
* Author: Hüseyin Babal
* Author information: NodeJS, PHP, Java, Elasticsearch, WordPress Plugin/Widget Development, MySQL, MongoDB, SEO, Agile Software Development, Cloud Integration, SCRUM.CSM.

> Directives are one of the most powerful components of AngularJS, helping you extend basic HTML elements/attributes and create reusable and testable code.

> So, what is the link function there? Simply, the link function is the function that you can use to perform directive-specific operations. The directive is not only rendering some HTML code by providing some inputs. You can also bind functions to the directive element, call a service and update the directive value, get directive attributes if it is an `E` type directive, etc.

> Every directive has its own scope, but you need to be careful about the data binding with the directive declaration. 

> The main advantage of the directive is that it's a reusable component that can be used easily.

> When you use directives inside the template, what you see on the page is the compiled version of the directive. Sometimes, you want to see the actual directive usage for debugging purposes. In order to see the uncompiled version of the current section, you can use `ng-non-bindable`.

#### [BLOG17] Creating Custom AngularJS Directives Part I - The Fundamentals
* Access date: September-2015
* URL: http://weblogs.asp.net/dwahlin/creating-custom-angularjs-directives-part-i-the-fundamentals
* Author: Dan Wahlin
* Author information: JavaScript/ES6, Node.js, Angular, HTML5, jQuery, Node.js, ASP.NET MVC, C#.

> AngularJS directives can be a bit intimidating the first time you see them. They offer many different options, have a few cryptic features (and cryptic is my politically correct term for what were they thinking here?), and are generally challenging at first.

> In addition to performing data binding operations with templates, directives can also be used to manipulate the DOM. This is done using the link function shown earlier.

#### [BLOG18] Directive Controller And Link Timing In AngularJS
* Access date: September-2015
* URL: http://www.bennadel.com/blog/2603-directive-controller-and-link-timing-in-angularjs.htm
* Author: Ben Nadel
* Author information: Adobe Community Expert as well as an Adobe Certified Professional in Advanced ColdFusion.

> I've talked about the timing of directives in AngularJS a few times before. But, it's a rather complicated topic, so I don't mind digging a bit deeper.

> As the DOM (Document Object Model) is compiled by AngularJS, the directive controllers and link functions execute at different parts of the compile lifecycle.

> This is an important difference. While you can only access the DOM tree in the bottom-up linking phase, the directive controller can provide a hook into the top-down lifecycle. This can be critical if you have to handle DOM events based on when elements of the DOM tree came into existence. The linking phase can never give you that because it's executed in reverse.

#### [Q&A1] Template Type Conversion Errors are Difficult to Debug
* Access date: September-2015
* URL: https://github.com/angular/angular.js/issues/1974

> Template type conversion errors are difficult to debug.

> FYI the only line in the stack trace that references my actual document (index.html, line 500), line 500 is past the end of the source document, so it's referencing some angular script injected into the header, thus does not seem to be useful for debugging.

#### [Q&A2] Why Don't AngularJS Errors in the HTML Show Up in the Console?
* Access date: September-2015
* URL: http://stackoverflow.com/q/26227596

> Expressions are meant to handle very simple logic, and are optimized for simplicity and not breaking your app.

#### [Q&A3] Separating JS Logic From Angular Templates
* Access date: October-2015
* URL: https://groups.google.com/forum/#!topic/angular/pHSMrphDJhM

> It seems as though the developers built the entire framework and wrote the documentation promoting the idea that it's A-OK to frankenstein JavaScript expressions into your HTML.

> Architecturally, the way jQuery solves problems is not the best. Clayton pointed out that it's difficult to test, but it also leaves intent nebulous. Directives extend DOM functionality (and we can test them within and without the view) and so belong within the DOM. When you use jQuery to programmatically insert on-click behavior, whoever is reading the view (designer or developer) doesn't know what something does. With AngularJS, that becomes quite clear.

#### [Q&A4] AngularJS Use of Inline JavaScript in HTML Attributes is not Bad Practice?
* Access date: October-2015
* URL: http://stackoverflow.com/q/14793692

> As I read through the Angular tutorials, I really like a lot of it, but isn't `ng-click` the equivalent of an inline `onClick`? My understanding was that the JavaScript community had determined inline JavaScript event handlers in your HTML was bad practice.

#### [Q&A5] AngularJS: Is mcode{ngClick a Good Practice Why is There no ng-event in AngularJS?
* Access date: September-2015
* URL: http://stackoverflow.com/q/14346073

> I understand that `ng-click` is technically not the same as `onclick`, but both are placed in the markup. I thought that would be a bad practice? Why is this one of the core concepts of AngularJS, if most people say this is bad? I thought it would be better to select the DOM element from JavaScript and not to place logic in the markup.


#### [Q&A6] How to not Let Angular Spoil All Your HTML With Logic Code?
* Access date: October-2015
* URL: http://www.reddit.com/r/angularjs/comments/2b15dv/how_to_not_let_angular_spoil_all_your_html_with/

> I'm relatively new to angular, and the more I use it the more I insert ng-this and ng-that into my HTML and soon I have a mess like this.

#### [Q&A7] Should AngularJS Logic Be Placed in HTML File?
* Access date: September-2015
* URL: http://stackoverflow.com/a/24845815

> I am very new to AngularJS. Now when I saw the code, I was very curious about all the logic that is placed in the HTML code.

> Now about adding logic to the views, if we are talking about business logic then it's a big no no. Use a method on your controller that will evaluate stuff using the service.

> If we are talking about `ng-if`/`ng-show` conditions then only if they are small and readable conditions I would add them to the view. When it's more than that, I move them to the controller for debugging issues and since I believe the HTML should be readable.


#### [Q&A8]Using scope.$watch and scope.$apply in AngularJS
* Access date: September-2015
* URL: http://stackoverflow.com/q/15112584

> I don't understand how to use `\$scope.\$watch` and `\$scope.\$apply`. The official documentation isn't helpful.

#### [Q&A9] What Does $scope.$apply() Do?
* Access date: September-2015
* URL: http://stackoverflow.com/q/18710478
* Author: Dan Prince

> I've been using `\$scope.\$apply()` to update the bindings for my models when I receive data through websockets in my Angular apps and it works. But what does it actually do and why does it need to be called to achieve the update? 

#### [Q&A10] Correct Way to Integrate jQuery Plugins in AngularJS
* Access date: October-2015
* URL: http://stackoverflow.com/q/16935095

> I was wondering what is the correct way to integrate jQuery plugins into my angular app. I've found several tutorials and screen-casts but they seem catered to a specific plugin. 

> If you are using a jQuery plugin, do not put the code in the controller. Instead create a directive and put the code that you would normally have inside the link function of the directive. 

#### [Q&A11:] Difference Between the controller, link and compile Functions When Defining a Directive
* Access date: October-2015
* URL: http://stackoverflow.com/q/12546945

> Some places seem to use the controller function for directive logic and other use link. The tabs example on the angular homepage uses controller for one and link for other directive. What is the difference between two?

