# Publish Script

## How to Add to Pyegi feed

In order to add your script to the Pyegi feed, you may follow one of these paths:

* Ask Pyegi developers directly to add your script link on Github to the feed. The advantage of this path is that if you develop another script, you don't need to ask the Pyegi developers to add your script link to the Pyegi feed. Instead, you may include the link in the `known-feeds` field of the PyProject file of your previously added script to the feed.
* Ask someone whose script link is in the Pyegi feed to include your script link in their PyProject file. In this case, you have a limitation. If there are no script links under your user in the Pyegi feed, you may include 7 of your scripts in **known users**' PyProject files.

It should be noted that if your script link is present in Pyegi main feed as well as in the `known-feeds` field of other scripts, the link present in Pyegi main feed will have priority.

## Tags are recommended!

We recommend defining tags for each version of your script. If you have tags for your script, Pyegi lists them in its feed. If, however, you don't include tags, things get complicated. If Pyegi encounters multiple reference to one tag-less script with different links, if the script's link is present in Pyegi's main feed, that link is given priority; if not, the most updated link will be given priority.
