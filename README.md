# pantip_scraper
# Original version by DarkDrag0nite

This is web scraper for pantip written in python2 https://github.com/Bankde/pantip_scraper.git

# How to use

`Before anything: If you get any error, feel free to raise issue/bug or mail me. Usually it's not your fault. Pantip Web developers also change their code from time to time. I will try to update pantipScraper to match current pantip code.`

To get a topic: python pantipScraper.py topic_id

Example: `python pantipScraper.py 35000000`
	
Start from: python pantipScraper.py -start topic_id

Example: `python pantipScraper.py -start 35000000`
	
End at: python pantipScraper.py -start topic_id -end topic_id

Example: `python pantipScraper.py -start 35000000 -end 35001000`

Without comment: -noComment

Example: `python pantipScraper.py -noComment -start 35000000`

<br />

Example of reading JSON is in readExample.py

Another example of reading JSON (plain text style): 

    PYTHONIOENCODING=UTF-8 python readExample2.py > result_of_readExample2

# Features

The data will be store in pantip_storage as JSON.

Right now it could extract
- topic name
- author
- story
- like Count
- emotion Count
- emotions (count of each types)
- tags
- comments count
- comments

Extra Feature
- Could Handel connection problem (test on OS X, not confirm on linux/windows)

# Limitations

- no image being extracts (I can't decide how to save image properly and how to link that image to topic)
- no poll information and topic with poll might be extracted incorrectly
- no reply to comment yet (sry, I'm working on it) `Updated have reply comments `

# Json Structure

JSON structure is as following:

== Topic ==
- tid (อันนี้หมายถึง topic id)
- name (topic name)
- author
- author_id
- story
- likeCount
- emoCount
- emotions (as Emotion object)
- tagList (as array of string)
- dateTime
- commentCount
- comments (as array of Comment object)

<br />

= Comment ==
- num
- user_id
- user_name
- replyCount
- replies 
    - num
    - user_id
    - user_name
    - replyCount
    - replies
    - message
    - emotions (as Emotion object) 
    - likeCount
    - dateTime
- message
- emotions (as Emotion object) 
- likeCount
- dateTime

<br />

== Emotion ==
- like
- laugh
- love
- impress
- scary
- surprised

# Credit, Feedback, Suggestion is appreciated.
