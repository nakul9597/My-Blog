---
layout: post
permalink: "/gsoc/final_report"
title: "GSoC Final Report"
---
<center><img src="{{site.baseurl}}/gsoc_logo.png" width="350" align="left"><img src="{{site.baseurl}}/ruby_logo.png" width="350"></center>

**Organisation** : [`Ruby`][ruby_org_gsoc]

**Project**: [`rubygems.org`][rubygems_github]

**Project page**: [`Recursive tree view for gem dependencies`][gsoc_project]

**Mentors**: [`Aditya Prakash`][aditya] and [`Qiu Chaofan`][qiu]

<h2>Recursive tree view for gem dependencies</h2>

<h3>Abstract</h3>
This project would add a feature on the rubygems.org website to give an option on each gem web page to show a tree/DAG of all transitive dependencies needed by that gem. In one of the [`issue`][issue] that lead to this project, a user talks about how some users download a gem based of it’s transitive dependencies and how they need to keep a mindmap of these transitive dependencies to conclude whether or not to use the gem. This project will help such users get a better idea of whether that gem is for them or not.

<h3>Road Map</h3>
&nbsp;&nbsp;&nbsp;**Front end**
* List of dependencies for that particular gem
* Arrow before each dependency which when clicked will display all of that gem's dependencies
* This keeps happening for all dependencies on the page. Once a dependency is clicked, it can't be clicked again (only toggled for hiding its dependencies).
* All dependencies are divided by runtime or development scope
* Both dependencies and scopes are togglable

&nbsp;&nbsp;&nbsp;**Back end**
* Write a controller to use gem name and version to find its dependencies
* Use rubygem code to find best version for each dependency based on it's requirement
* Controller should render html and json (for ajax clicks)
* write functional and integration tests

<h3>The Story So Far</h3>
* First created a web page that displays all the transitive dependencies list in ascending order
  * It was taking too long to load and not very user friendly
* Created basic webpage with toggling
* Added ajax request to find transitive dependencies but creating a js file in view
* Made toggling possible to open and close dependencies
* Moved the js file to asset pipeline thus making ajax requests client side
* Added functional test case for controller and integration test for js
* Seperated view as runtime and development dependencies, also togglable to be hidden

<h3> Code Contribution </h3>
* [**Pull request**][project_pr]
* [**Project file changes**][change_file]
* [**First commit**][c1]
* [**Last commit**][lc]
* [**Major commits**][commit]

<h3>Acknowledgement</h3>
I'd like to thank my mentors Aditya Prakash and Qui Chaofan for always monitoring my progress, immediately responding and guiding me whenever I needed help. I know I asked a lot of doubts and they helped me every time. I also know I must have been a little difficult to work with, so thank you for having the patience. I owe my wholehearted thanks and appreciation to the entire team of ruby and rubygem.org for selecting me for this project and for their assistance during the entire project work.

[ruby_org_gsoc]: https://summerofcode.withgoogle.com/organizations/5542255322988544/
[rubygems_github]: https://github.com/rubygems/rubygems.org
[gsoc_project]: https://summerofcode.withgoogle.com/projects/#4782705487642624
[issue]: https://github.com/rubygems/rubygems.org/issues/937
[aditya]: https://github.com/sonalkr132
[qiu]: https://github.com/ecnelises

[change_file]: https://github.com/rubygems/rubygems.org/pull/2029/files
[project_pr]: https://github.com/rubygems/rubygems.org/pull/2029
[commit]: https://github.com/rubygems/rubygems.org/pull/2029/commits
[lc]: https://github.com/rubygems/rubygems.org/pull/2029/commits/a50e82ea387a0c21745bf92e4dcfd94ab7782469
[c1]: https://github.com/rubygems/rubygems.org/commit/7d73dd270e711c7127225d042ef93492f877d025
[c2]: https://github.com/rubygems/rubygems.org/commit/0cf105832372571b9692cc243723cdb760004211
[c3]: https://github.com/rubygems/rubygems.org/commit/8a225c728652b5ec97de1ce386af9a25f1872cbc
[c4]: https://github.com/rubygems/rubygems.org/commit/3bc1dc38e7519b85e4d422be2c3bded9e7c5af45
[c5]: https://github.com/rubygems/rubygems.org/commit/bd9c2aff381d8d3bacff47f809af0a45358722b2
[c6]: https://github.com/rubygems/rubygems.org/commit/dc88b78b60687a60b0932f871e036a85327c5d1d
[c7]: https://github.com/rubygems/rubygems.org/commit/e6d2eb74e507cdcd4e1ca680c87a65213174973b
[c8]: https://github.com/rubygems/rubygems.org/commit/a7b4a8436194f0e8ae0b0324e10496189372ccf6
[mc1]: https://github.com/rubygems/rubygems.org/pull/2029/commits/ccb2382eeb082016e651aed1cf48b03ea0940799
[mc2]: https://github.com/rubygems/rubygems.org/pull/2029/commits/b7993e47beba81f49baafdc22bd32056622b73e7
