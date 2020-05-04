# When You Need to Forget Events

TODO parse [https://www.michielrook.nl/2017/11/event-sourcing-gdpr-follow-up/](https://www.michielrook.nl/2017/11/event-sourcing-gdpr-follow-up/)

## The Problem

Event Sourcing makes a whole class of compliance problems easier, but it complicates another. We have seen the rise of privacy regulations in the past few years \(a good thing!\), such as the GPDR and the CCPA.

These laws provide the _right to be forgotten_ \(GDPR\) and the _right to deletion_ \(CCPA\). This is hard when you adopt event sourcing, since one of the central teachings is _Thou shalt make thy events immutable_.

This problem is not too different from versioning events.

De-anonymisation, such as scrubbing the data, is not always good enough. For example, see the [AOL leak](https://en.wikipedia.org/wiki/AOL_search_data_leak), where users were de-identified, yet journalists were able to able to find the people behind the anonymous identifiers. [This Nature Communications article](https://www.nature.com/articles/s41467-019-10933-3.pdf) is another good reminder that anonymised data is not as anonymous as you think.

## Don't collect private data in the first place

Do you really need to collect your users' IP address, their SSN, and their mother's maiden name when they visit your website? Discuss with your domain experts if the data you take in is really needed.

This approach is conflicting with the "let's store all events and data, you never know when we want to analyse this"-approach suggested before.

## Deleting Events

Here we'll go against the event sourced grain and delete events anyway.

TK state why this is bad

## Sliding Window

Some domains don't need all data.

Let's say you're working in an analytics domain. You only aggregate data for every month and only go back 6 months. Do you still need the data from a year ago?

Note that is different from deleting events \(above\). When using a sliding window or retention period, your current state is not dependent on the deleted events.

## Compacting Events

TK Hmm, something about compaction and snapshots could be used to though I haven't seen it.

## Scrubbing Events

Instead of deleting events, we clean them. We update them in-place to remove personal information.

## Using a pointer to externally managed data

TK similar as one would do for an uploaded file

## Dropping the Key

We encrypt the sensitive information. When a deletion request comes in, we delete the encryption key.

### Further ~~reading~~ watching

* [https://www.youtube.com/watch?v=\_czdzNUZGFs](https://www.youtube.com/watch?v=_czdzNUZGFs)
* [https://www.youtube.com/watch?v=FTcBa-2-I2c](https://www.youtube.com/watch?v=FTcBa-2-I2c)
* [https://www.youtube.com/watch?v=vbR2UGedy5g](https://www.youtube.com/watch?v=vbR2UGedy5g)

