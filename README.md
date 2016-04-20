<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#orgheadline15">1. ExVocabulary</a>
<ul>
<li><a href="#orgheadline6">1.1. What is it</a>
<ul>
<li><a href="#orgheadline1">1.1.1. Hyphenation</a></li>
<li><a href="#orgheadline2">1.1.2. Part of speech</a></li>
<li><a href="#orgheadline3">1.1.3. Usage example</a></li>
<li><a href="#orgheadline4">1.1.4. Synonyms</a></li>
<li><a href="#orgheadline5">1.1.5. Antonyms</a></li>
</ul>
</li>
<li><a href="#orgheadline7">1.2. Features</a></li>
<li><a href="#orgheadline10">1.3. Installation</a>
<ul>
<li><a href="#orgheadline8">1.3.1. Using <code>pip</code></a></li>
<li><a href="#orgheadline9">1.3.2. Install from source</a></li>
</ul>
</li>
<li><a href="#orgheadline13">1.4. Demo</a>
<ul>
<li><a href="#orgheadline11">1.4.1. API Key importation</a></li>
<li><a href="#orgheadline12">1.4.2. Usage</a></li>
</ul>
</li>
<li><a href="#orgheadline14">1.5. License</a></li>
</ul>
</li>
</ul>
</div>
</div>


# ExVocabulary<a id="orgheadline15"></a>

A module to fetch word definition, antonym, synonym and example from online API.

This module is inspired by [Vocabulary](https://github.com/prodicus/vocabulary); With most of original functionality, adds
API key import and retrieves example from [vocabulary.com](http://vocabulary.com).

This module is one of the backend of FlashCard to search the word without definition

## What is it<a id="orgheadline6"></a>

For a given word, using ExVocabulary, you can get it's

### Hyphenation<a id="orgheadline1"></a>

Shows the particular stress points (if any)

### Part of speech<a id="orgheadline2"></a>

Gives the definition of the word, whether the word is a noun, interjection or an adverb et el

### Usage example<a id="orgheadline3"></a>

A quick example on how to use the word in a sentence and where the sentence from

### Synonyms<a id="orgheadline4"></a>

Gives the synonyms of the word for different part of speech (if any)

### Antonyms<a id="orgheadline5"></a>

Gives the antonyms of the word for different part of speech (if any)

## Features<a id="orgheadline7"></a>

1.  As a module of python
2.  Return JSON objects
3.  Minimum dependencies (just uses requests module)
4.  Easy to install
5.  Stupidly easy to use

## Installation<a id="orgheadline10"></a>

### Using `pip`<a id="orgheadline8"></a>

    pip install exvocabulary

### Install from source<a id="orgheadline9"></a>

    git clone https://github.com/adavis10006/ExVocabulary.git
    cd ExVocabulary
    pip install requests
    python setup.py install

## Demo<a id="orgheadline13"></a>

### API Key importation<a id="orgheadline11"></a>

In order to support various API keys, ExVocabulary isolates API keys to a JSON
file, as example

    // {"API_name": [ ["API_key", api_status], ...]}
    {
        "wordnik": [
            ["1e940957819058fe3ec7c59d43c09504b400110db7faa0509", 1],
            ["a2a73e7b926c924fad7001ca3111acd55af2ffabf50eb4ae5", 1]
        ],
        "bighugelabs": [
            ["eb4e57bb2c34032da68dfeb3a0578b68", 1]
        ]
    }

It supports multiple API keys importation

### Usage<a id="orgheadline12"></a>

    from exvocabulary import ExVocabulary

    vb = ExVocabulary("api_key.json")

    vb.hyphenation("love")
    # >>> '[{"text": "love", "seq": 0}]'
    vb.part_of_speech("love")
    # >>> '[{"text": "noun", "example:": "A deep, tender, ineffable feeling of affection and solicitude toward a person, such as that arising from kinship, recognition of attractive qualities, or a sense of underlying oneness.", "seq": 0}]'
    vb.synonym("love")
    # >>> '{"verb": ["love", "enjoy", "roll in the hay", "make out", "make love", "sleep with", "get laid", "have sex", "know", "do it", "be intimate", "have intercourse", "have it away", "have it off", "screw", "jazz", "eff", "hump", "lie with", "bed", "have a go at it", "bang", "get it on", "bonk", "copulate", "couple", "like", "mate", "pair"], "noun": ["passion", "beloved", "dear", "dearest", "honey", "sexual love", "erotic love", "lovemaking", "making love", "love life", "concupiscence", "emotion", "eros", "loved one", "lover", "object", "physical attraction", "score", "sex", "sex activity", "sexual activity", "sexual desire", "sexual practice"]}'
    vb.antonym("love")
    # >>> '{"verb": ["hate"], "noun": ["hate"]}'
    vb.vocabulary_example("love")
    # >>> '[{"corpus": "New York Times", "seq": 0, "sentence": "\\u201cThe market seems to love artists who make very little work and don\\u2019t seem to have a life and never go out,\\u201d he said."}, {"corpus": "New York Times", "seq": 1, "sentence": "There are two pairs of funny dwarves and two imperious villainesses and a love interest for the title character."}, {"corpus": "New York Times", "seq": 2, "sentence": "Ms. Genzken titled one of her books \\u201cI Love New York, Crazy City,\\u201d and her soaring, scale-scrambling blossoms may have you saying the same."}]'

## License<a id="orgheadline14"></a>

The MIT License (MIT)

Copyright (c) 2016 Davis

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
