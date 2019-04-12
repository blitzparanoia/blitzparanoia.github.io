---
layout: post
title:      "Will It Run?: CLI Project Experience"
date:       2019-04-12 13:48:37 -0400
permalink:  will_it_run_cli_project_experience
---


Working on the first project of the program was in one word...intimidating. It was daunting looking at an essentially blank file. The tutorials to help set up the ruby gem were very helpful. After hours of watching videos, walkthroughs and reading I had to start working. Being a bit of a visual person I took the time to pencil and pen my idea the ‘old-fashioned’ way into a chart with expectations and accompanying questions.

This particular lab involved the practice of web scraping which in the extraction of data from a website. The tool being used in this scenario is Nokogiri to break down the site and extract the information.

First, was ensuring the chosen website could be scraped. During this process I learned all not websites are created equal. Sites that are not good candidates include a user disallow in their robots.txt file, too much JavaScript, inconsistent use of classes/tags and sites that update their pages (changing placement of data).

### Making The Gem: Pry And Nokogiri
Creating the gem using “bundle gem name_of_gem” command had made the basic file tree requirements. The gem includes 3 main files: scraper, cli and the main class.
It helped tremendously to have each file/class/method responsible for only one job, this practice was advised and made it possible to keep track of the program when running into errors. 

Building a project from scratch meant there is no access to the learn command and there is no rspec (unless I create one) to test if I am on the right track. However, proper use of Pry was of great assistance. Pry had allowed for the ability to code and stop the program at points in order to see which variables were being stored. In the Pry session the user is able to manipulate the information to test what code would output or if it would even function. Especially when diving into the “Nokogiri jungle” searching to locate the proper elements and tags for the desired information.

### Overall
After running into a million error messages, reading tons of forms/documentation, watching hours of videos and reaching out for help from the cohort; the project was complete. The ability to take everything that was taught up to this point and be able to be it together felt very satisfying. Every new error message was motivation. Every break taken to refresh my thoughts helped to see code clearer. Every help session was fuel. Fuel to move on with positivity knowing that it is possible to achieve the desired outcome.

### The CLI Gem- What Does It Do?
The gem is called `zodiac_search` it works by scraping a list of zodiac signs from a website using Nokogiri. The user is prompt to select a number from the list. When a number is selected the sign name, date range and strengths/weaknesses are displayed. The data displayed is scraped as per the choice made by the user.

