# Answers

My Unix username: serzh_harutyunyan

Public RSS feed URL: https://the.hell.am/~serzh_harutyunyan/news.xml

Public podcast feed URL: https://the.hell.am/~serzh_harutyunyan/podcast.xml

RSS reader and operating system used: NetNewsWire, iOS

Podcast player and operating system used: Apple Podcasts, iOS

## RSS

1. Where did you find the first and second `<item>` elements in `news.xml`?

Both are inside the `<channel>` element, after the channel's title, link and description. Each line of news.txt became one `<item>` with its own title, description and guid.

2. What is `<guid>` for? What happens if an old GUID changes?

The GUID is a unique identifier for each entry, so the reader can tell entries apart and know which ones it has already shown. If an old GUID changes, the reader thinks it is a new entry and shows the same post again as a duplicate, possibly marked unread.

3. What did you observe after refreshing the feed reader?

After running make_news.py again and refreshing, the second post appeared in the reader next to the first one. I didn't have to notify the app; it fetched the XML and found the new item.

## Podcast

4. What is the difference between an ordinary RSS item and a podcast RSS item?

A podcast item has an `<enclosure>` element that points to a media file, with its URL, its size in bytes (length) and its MIME type (audio/mpeg). A normal news item only has text (title, description, guid).

5. What is the value of `length` in your first `<enclosure>`? What does it measure?

length="21115". It is the size of episode1.mp3 in bytes, and it matches the Content-Length: 21115 that curl -I returned.

6. What changed in the XML after you added the second episode?

A second `<item>` appeared with its own title ("My second episode"), its own GUID (episode-2), its own pubDate and an enclosure pointing to episode2.mp3 with length 62455.

7. Did you hear both waves in your podcast app? How are the sounds different?

Yes. The sine wave (440 Hz) is a smooth, pure, higher tone. The square wave (220 Hz) is an octave lower and sounds harsh and buzzy, because the abrupt jumps between +1 and -1 add many higher harmonics.

## Screenshots

![RSS app](screenshots/rss.png)
![Podcast app](screenshots/podcast.png)
