# When You Need to Forget Events

## The Problem

Event Sourcing makes a whole class of compliance problems easier, but it complicates another. We have seen the rise of privacy regulations in the past few years \(a good thing!\), such as the GPDR and the CCPA.

These laws provide the "right to be forgotten" \(GDPR\) and the right to deletion \(CCPA\). This is hard when you adopt event sourcing, since one of the central teachings is _Thou shalt make thy events immutable_.

This problem is not too different from versioning events.

## Don't collect data in the first place

Do you really need to collect your users' IP address, their SSN, and their mother's maiden name when they visit your website? Discuss with your domain experts if the data you take in is really needed.

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

## Dropping the Key

We encrypt the sensitive information. When a deletion request comes in, we delete the encryption key.

### Further reading

* [https://www.youtube.com/watch?v=\_czdzNUZGFs](https://www.youtube.com/watch?v=_czdzNUZGFs)
* [https://www.youtube.com/watch?v=FTcBa-2-I2c](https://www.youtube.com/watch?v=FTcBa-2-I2c)
* [https://www.youtube.com/watch?v=vbR2UGedy5g](https://www.youtube.com/watch?v=vbR2UGedy5g)

