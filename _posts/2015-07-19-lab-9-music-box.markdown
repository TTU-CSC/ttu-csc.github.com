---
layout: post
title:  "Lab 9: Music Box"
date:   2015-07-19 13:10:30
categories: docs
---

We will be making a small music box. We will simply be using the piezo element with some software for this lab.

We will need to create a struct, which will allow you to store both a frequency and duration into a single element of an array, since we will be using an array to represent the notes of a song.

    struct Note
    {
    	unsigned int frequency;
    	unsigned int duration;
    };

