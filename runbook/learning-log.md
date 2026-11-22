# Learning log

One idea per entry, in plain English, so Terry can reread it any time.

## Save it where it lives (Nov 21, 2026)

A file on Claude's computer is like a draft on a hotel notepad: when the
session ends, it is gone. Work only counts once it is **committed** (a saved
snapshot with a note saying what changed) and **pushed** (that snapshot copied
up to GitHub, where the website is served from). That is why every step of
this build ended with a commit and a push. When the World Newswire Press repo
was not yet open to Claude, the work was pushed to a backup branch instead of
being left on the notepad. Without that, a closed browser tab would have
erased the whole site.

## The sign on the door: noindex and canonical (Nov 21, 2026)

A story page on our site shows another outlet's headline and teaser. To
Google, a copy of someone else's headline looks like a photocopy of their
work, and sites full of photocopies get marked down. So each story page
carries two small notes for search engines in its `<head>` (the hidden top
of the page): **noindex** ("do not list this page in search results") and a
**canonical** link ("the real version lives at the outlet's address"). Readers
still get the page; search engines credit the original. Without those two
lines, hundreds of near-copies could drag down the whole site's ranking.

## Nov 22, 2026 — One light switch for ads
Google ads need one small line of code in the hidden top section of every page (the "head"), plus a file called ads.txt that proves to advertisers we really sell space through Google. Instead of pasting that line into every page by hand, there is one switch: ADSENSE_PUB at the top of wire.py. Fill it in and run tools/adsense.py, and every page gets the line between two marker comments; empty it and run again, and it all comes back out. The markers work like labels on a fuse box: the tool always knows which wire is its own. Releases stay ad-free, because a client paid for that page.
