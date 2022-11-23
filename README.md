# Multilingual Decentralized Login 

This is a multilingual version of the decentralized login form.

## Purpose

The goal is to illustrate how to support multiple languages on a login form. In this cases the languages are:
- Chinese
- English
- French
- Korean
- Spanish

## Background

This is part of a project by FutureSense for the National Police Agency big data portal.


A previous version of this system used DID (Decentralized Identity) protocols, but these protocols are rather complex, both for developers and for users.

This version narrowed the scope to *login with Web3 wallet* rather than login with DID. The wallet chosen for this initial version was Metamask, because it is by far the dominant wallet (among 200 wallets in the sector), with around 90% market share (about 30+ million users).

## Constraints

The objective here was to create a login form using only HTML, CSS and Javascript, with no other dependencies, so that this form can be easily incorporated into a larger, more complex system. 

There were two previous versions of this system:
1. DID Login with Springboot
2. DID Login with JSP

Both of these proved challenging for the portal team to incorporate into the portal.

## How it Works

There are 2 simple techniques used.
1. CSS-Based: using visibility of a DIV controlled by CSS style attribute
2. Javascript: using a Javascript object consisting key/value pairs 

### DIV and CSS technique ###
For on-page content in HTML, there are multiple DIVs, one for each language, with IDs that indicate the content as follows:

1. **content_EN** : English
2. **content_SP** : Spanish
3. **content_FR** : French
4. **content_KR** : Korean
5. **content_CN** : Chinese

Each DIV containsc content in that language. Initially the DEV with the default language (content_EN) is displayed (using CSS *display:"block"*) and the others have the display attribute set to "none".

There are HTML buttons at the top of the form to select one of the five supported langauges.

These toggle the visibility of the various DIVs in order to display the selected language.

### Javascript object with key/value pairs  ###

The second technique is for Javascript code that outputs error messages to the browser using the *alert()* function.

The error messages in multiple languages are stored in key value pairs, where key is a language selector such as "EN" or "KR". The value is a string in the desired language.

There is a selector variable *current_language* that is set when the language button is clicked.

Then, when the code needs to output a message in a language, it does something like:

    alert(msg_not_installed[current_language]);
or
    alert(msg_wallet_busy[current_language]);

### Limitations of these techniques ###

These techniques are simple and they work. They are a good choice for a narrow scope or small number of pages. They will not scale to a large amount of content.

There are other well established techniques that are more complex, such as using properties and creating parallel folders with content.

An in-between technique that also works is to have parallel files that are redirected by javascript code in response to button action. These parallel files can be driven by plain text files and macro variables (such as the ubiquitous m4 macro processor). Having all the content in plain text files makes it easy to process. For example, running through Google translate. Google translate will leave alone long variable names and translate the actual content. 

FYI, here is a link to the m4 macro processor:

    https://www.gnu.org/software/m4/manual/m4.html








#### This file is at https://github.com/rayvalfs/multilingual_login/README.md ####