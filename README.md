# NRELabs Youtube Channel Translations

## Introduction

So you want to contribute translations to our youtube channel so non-native English speakers can get the most out of the content?  This is the place!  We'll talk about the file format to write your translations in, then we'll talk about how to contribute to this repository.

## The file format

The first thing you'll want to do is understand the SubViewer file format.  You can start by looking at the example on Youtube's website, [here](https://support.google.com/youtube/answer/2734698?hl=en&ref_topic=7296214).  Note that it should be in subviewer v1.0 format, which means no markup is supported at all.  Here's an example:

---
```
0:00:00.599,0:00:04.160
>> ALICE: Hi, my name is Alice Miller and this is John Brown

0:00:04.160,0:00:06.770
>> JOHN: and we're the owners of Miller Bakery.

0:00:06.770,0:00:10.880
>> ALICE: Today we'll be teaching you how to make
our famous chocolate chip cookies!

0:00:10.880,0:00:16.700
[intro music]

0:00:16.700,0:00:21.480
Okay, so we have all the ingredients laid out here
```
---

Let's take the first line as an example.  We see two timestamps, separated by a comma.  These timestamps are relative to the start of the whole video.

```
0:00:00.599,0:00:04.160
>> ALICE: Hi, my name is Alice Miller and this is John Brown
```

The first timestamp is the "start" time for the associated text to be displayed: "0:00:00.599".  The second timestamp is when the text should "stop" being displayed: "0:00:04.160".

The only other rule you need to know is that there is a single blank line between each caption, as can be seen above.

## Fork and Clone the repository

Log into github, navigate to this repository, and click "fork" in the upper right portion of the browser.  You should now have a copy of this repository under your account.  Now clone this repository on to the computer that you'll be doing the transcription work on.

```
cloudtoad@debian-dev:~$ git clone git@github.com:cloudtoad/youtube-translations.git
cd youtube-translations
```

## Open an issue on the original repository's page to let people know what you're doing

Before you start your work, you should let the community know what you're working on.  This way, two people don't end up working on the same thing at once.  Go to [https://github.com/nre-learning/youtube-translations](https://github.com/nre-learning/youtube-translations) and click '**Issues**'.  Then click '**New issue**'.  Put some explanatory text in with a link to the video, the title of the video, and the unique video identifier (which you can find following the instructions in the next paragraph).

## Create a directory for the video and add a translation.

Each video in youtube has a unique identifier.  To see this identifier, simple copy a link to the video.  In this example, we'll look at the recent interview we did with Jay Taylor about his experiences learning Python.  Here are some links to this video:

```
https://youtu.be/udn3Q9ARayU  
https://www.youtube.com/watch?v=udn3Q9ARayU  
https://www.youtube.com/watch?v=udn3Q9ARayU&feature=youtu.be
```

The unique identifier for this video is **udn3Q9ARayU**.  In the project directory on your computer, look to see if a directory with this name already exists.  If it doesn't, we'll have to create the directory.  On linux this looks like this:

```
cloudtoad@debian-dev:~/youtube-translations$ pwd
/home/cloudtoad/youtube-translations
cloudtoad@debian-dev:~/youtube-translations$ mkdir udn3Q9ARayU
cd udn3Q9ARayU
```

If this is a new directory, we need to create a README.md file.  In our example, one already exists.  It tells us what video it is with the title and description from youtube, plus a link to the video.

```
example readme.md for video
```

Once that is done, it's time to add a translation to this directory!  Let's suppose you're contributing a French translation.  Create a directory "French"

```
cloudtoad@debian-dev:~/youtube-translations$ pwd
/home/cloudtoad/youtube-translations/udn3Q9ARayU
cloudtoad@debian-dev:~/youtube-translations$ mkdir French
cd French
```

Ok, now create your SubViewer file here!  It should be named "French.sub"

## Contributing your work to the Community

When you're all done, it's time to checkout a branch, commit your changes, and open a pull request.

```
git checkout -b udn3Q9ARayU-French
git add *
git commit -m "Created French translation for video udn3Q9ARayU."
git push origin udn3Q9ARayU-French
```

Now you should see your file in your own github fork of the repository.  Open a Pull Request to have your contribution reviewed and added to the video on Youtube.

If you have any questions, please ask!  Go to [https://community.networkreliability.engineering](https://community.networkreliability.engineering) and post your question.

We can also be reached via chat on our Discord server by following this invite:   [https://discordapp.com/invite/fRuSUyD](https://discordapp.com/invite/fRuSUyD).


Thanks for contributing!
