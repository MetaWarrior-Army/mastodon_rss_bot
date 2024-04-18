# mastodon_rss_bot
A mastodon rss reader & toot bot.

Very simply, a script that reads a list of RSS feeds and toots anything new!

We use Redis to remember old posts.

## CREDITS 
 Major inspiration to be found below.
 - https://github.com/hanscees/mastodon-bot

## Examples
MetaWarrior Army uses this project to run news bots at the following accounts:

- https://mastodon.metawarrior.army/@technewz_bot
- https://mastodon.metawarrior.army/@biznewz_bot
- https://mastodon.metawarrior.army/@worldnewz_bot

## DEPENDENCIES
```
import time, os, re, json, csv, requests, redis, pickle, argparse

from mastodon import Mastodon
from datetime import datetime
from dateutil import parser

import feedparser
import tokenlib_public
```

## MASTODON AUTH
as you can probably guess:
tokens are storen in `tokenlib_public.py`
You will need to create	this file first. Example can be	found in `tokenlib_public_example.py`
This is	where you set your bot name.

## Redis
You must have a local Redis server to run this script. The redis DB password is stored in `tokenlib_public.py`. 

## RUNNING
First, initialize the Redis DB using
`./run.sh i`

This will initialize the Redis DB and store the first batch of news. From this point you can run the command normally, which will only post new stories every 1 minute.

`./run.sh`

New posts are collected and tooted out every 20 seconds.

Edit `run.sh` to adjust sleep to increase or decrease interval.


