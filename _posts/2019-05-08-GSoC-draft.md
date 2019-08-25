---
layout: post
permalink: "/gsoc/draft2019"
title: "GSoC Project Draft"
---
<h2>Recursive tree view for gem dependencies</h2>

><h3>Contact:</h3>

Name: Nakul K Warrier<br>
Email: nakul9597@gmail.com<br>
Slackid: nakul9597<br>
Blog: [`https://nakul9597.github.io/My-Blog/`][blog_link]

><h3>What project do you want to work on?</h3>

This project would add a feature on the rubygems.org website to give an option on each gem web page to show a tree of all transitive dependencies needed by that gem. In one of the issues #937 that lead to this project a user talks about how some users download a gem based of it’s transitive dependencies and how they need to keep a mindmap of these transitive dependencies to conclude whether or not to use the gem. This project will help such users get a better idea of whether that gem is for them or not.

><h3>Why do you like Ruby, and why do you want to work on a Ruby project in GSoC 2019?</h3>

Firstly, I would like to say that I have a “no idea why” liking towards ruby than any other languages. It could be because Ruby is first high level language that I learnt after C++. As the first language that I begin working with I immediately started liking it. Whenever I get a project I try to work on it with ruby rather than any other language. I also like that fact that everything is an object in ruby. This might be silly but I love that ruby has aliases for some methods making it so easy toremember.

I want to work on a ruby project this GSoC mainly because it is the language that i know most and the always active community that is
ready to help anybody.specifically I want to work on this project because I have some knowledge on rails and postgresql.

><h3>Describe your experience with the following: Ruby, C, other languages:</h3>

**Ruby:**
- I have been practicing ruby since past 3 years and have done a lot of exercises on exercism.io in ruby language. My solutions are in this Githublink.
- I scripted a redis server with ruby to work with the redis-client calls for some commands.Github Linkto thisproject.
- My blog which is not updated is done using jekyll gem from ruby.

**C/C++:**
- The first language I learnt was C. It was the base for my learning of other high levellanguages.
- In class 11th and 12th we were taught C++ and I was very fascinated by data structures(especially linkedlists).
- I’ve done a lot of programming using C/C++ during my school and college days.

**Python:**
- I’ve done a lot of projects on python mainly because all my friends know onlypython.
- I did a project for converting the image to json using image recognition and regex in python for billingforms.
- In one project Movie Review data sets from IMDB were used, converted to a feature set and fed to a naive bayes classifier model in python NLTK toolkit. The trained model was then tested using some feature sets and the accuracy of the prediction (good review/ bad review) wasreturned.

><h3>Educational background:</h3>

I did major of my schooling in Chennai,Tamil Nadu, India. My 4th to 10th grade education was in Chinmaya Vidyalaya and my higher secondary in Vivekananda Vidyalaya. In my higher secondary I chose Chemistry, Physics, Maths, English and Computer science. I had a very good teacher for CS which helped me score very well in the subject. I was the top scorer of all time for my school in CS for my final exam.

I am doing my undergrads from SRM Institute of Science and Technology, Chennai. This is my final year and I’ve learnt a lot in the 4 years I’ve been here.

><h3>Have you sent pull requests to any Ruby open source projects?</h3>

No, I have not but I’ve always wanted to and GSoC has helped me get two very smart mentor to help me contribute to this ruby open source project. I actually had no idea on how to contribute to open source and all of a sudden in fourth year I hear of GSoC. I never knew about the communities in IRC and slack that is ready to help any newbie. Now that I have got the opportunity I will use it to best of my abilities.

><h3>What other commitments do you have this summer aside from GSoC?<h3>

I don’t have any plans this summer to be honest. I might be going to Australia to pursue my masters. If I get through GSoC I will be fully committed to finishing this and other projects if I have more time.

><h3>Are you planning any vacations or trips for fun this summer?</h3>

No vacations.

><h3>How many classes are you taking this summer?</h3>

I am not taking any classes.

><h3>Do you have any other employment this summer?</h3>

No as of now. I won’t be applying until GSoC is over.

><h3>Have you participated in GSoC before?</h3>

No, This would be my first time.

><h3>Proposal:</h3>

This project is based on giving users an option to find all transitive dependencies of a gem. This is done by creating a page where a DAG will show all the dependencies of that gem and the link is available on the every gem web page. It will help a lot of users decide if they want to download the gem for their project.

The hook is that different version of the same gem can also have different dependencies. So the DAG must not be generic to a gem. This is can be easily found as the database that stores all the data has stored it with different versions and its related dependencies in two different tables(dependencies and versions). When the new page to show dependencies is clicked the version also must be passed as an argument.

In the new page we show a limit depth of dependencies which can be expanded/minimised by the user. This can be coded with CSS and JS along with Embedded Ruby.

I’m a little familiar with rails and it’s MVC framework design. So I shouldn’t take a long time to understand how the app runs and how to code in the application. Also I’ve worked with postgres with rails in small detail but enough to know where to start and learn my way to work with
it. The part that will take a while is to design the webpage to look very user friendly and neat.

><h3>What is your expected timeline?</h3>

**Community Bonding (before 27th may)**

I’ve already cloned the rubygems.org rails app on my system and also updated the database thanks to help from my mentors. Before the first iteration I would like to get comfortable with:
- Railsworking
- Postgres
- Postgres coding inrails
- CSS and JS along withEmbeddedRuby(ERB).

**Iteration 1 - Simple dependencies page (28 may - 23 june)**

  * Create a new page in rubygems.org for dependencies treeview.
  * Use the postgresql database values to get list ofdependencies.
  * Use basic ERB, CSS and JS to show the dependencies on this webpage.
  * Provide the link on gemwebpage.
  * Start Writing test cases for theproject.

**First evaluation (24 june - 28 june)**

Hopefully, by this time we will be able to view the list of gem dependencies on a separate webpage. Some important test cases must run with assertions.

**Iteration 2 - Better designing (29 june - 21 july)**

  * Make the webpage in design sync with the rubygems.orgtemplate.
  * Get the design better by making depth limited dependencies in first view and others can be maximised/minimised according tothe
users wish. We could usethis viewor anaccordion menu.Arrow marks could be used for dependencies with further dependencies(which can be expanded) and circle for those without.
  * Create a DAG where dependencies don’t repeat each time. This could be achieved by highlighting dependencies(to show that it is already present as a dependency) that come to repeat each other and by not letting it expandfurther.
  * Classify the dependencies as runtime or development.
  * Finish writing test cases for theproject.

**Second evaluation (22 july - 26 july)**

By this time a fully functional web page for view of dependencies must be available for users to view. Test cases must run with assertions.


**Iteration 3 - Even better designing(27 july - 18 august)**

  * We could keepthis designas an option for users who want a better graphicalview.
  * Search bar for users to check if a gem is part of thedependencies.
  * Give details like total size the dependencies will take if the gem is downloaded.
  * Write final test cases for all the new ideas and features implemented.

In this final iteration, on working so much in this project me and my mentors would have come up with ideas that could be implemented. So I would implement those as well.

Also, I would give myself a week time before the final evaluation to check and test the project from scratch.

**Final Evaluation (19 august - 26 august)**

During this time the project should be completed, tested and verified by the mentors.

><h3>What are your hobbies, aside from coding?</h3>

I sketch a lot(portrait sketching). I am a singer and also part of a college band. I am part of crew that makes short films, where I do acting, writing, screenplay. I’m learning to play the guitar.

><h3>What I want to do with my life?</h3>

I have not yet decided.

><h3>Why choose you for this project? What makes you a good candidate?</h3>

I think that i’m a good candidate because I have at least a little prior experience in the fields related to this project from my past experiences. Also I have always wanted to contribute to open source but I never knew how to and had nobody to guide me. I am that type of person who can sit for hours debugging and coding without getting frustrated. For example: I once made a small home automation system using raspberry pi 3 and RoRovernight.

More importantly I am free for the whole term of GSoC and willing to spend all my time to finishing this project. I love to learn new things and spend time understanding the concept. I’m very sure i’ll be able to complete the project before the final review.

><h3>How do you think we can get more women interested in open source software development and science? How can we get more people from underrepresented groups involved?</h3>

I think that most women don’t get the opportunity to even get a glimpse of open source but if they did it might open up a realm of reality to them. Most women especially in India are not expected to do a lot of work and have very conservative parents. For those who are ready to learn, I think nobody is ready to guide them or they feel ashamed to ask somebody for help. Moreover, there is this stereotype that only men get into the field of computer science which has tochange.

I think that by the next generation the number of women/men who will take part will automatically increase because of the way of thinking in the current generation.

We could spread awareness to people around us to get them into open source. We could guide them and connect them with people who are ready to help.

[blog_link]: https://nakul9597.github.io/My-Blog/
