# Advantages of Event Sourcing

## Maps Mental Model

Events map closely to the mental model of the domain you're working in. _AudioMessageSent_ is clearer than _add a new row to the `messages` table with the `audio` column set to `TRUE`._

## You Don't Lose Any Data

Since your event store is append-only, you can't accidentally delete your `users` table - been there. But you also don't lose things you don't deem important at the moment.

## Audit Log For Free

An audit log is one of the things you'll need when you want to make your product [enterprise ready](https://www.enterpriseready.io/features/audit-log/) or compliant. An event sourced system makes this easy - your event stream, by definition, contains all actions that happened in your system. 

## Debugging Is Great Again

TK but harder if you have a lot of events

{% hint style="info" %}
A client emailed me. The attendances in a report did not add up! Using the event stream, I could tell them who added and removed people from the attendance list, on what date and with what account. They were thrilled with the detail I could provide them with and quickly concluded the report was correct, but they data they had fed the system was incorrect.
{% endhint %}

## Goodbye ORM mismatch

TK just create a new read model

## Offline and Offline-first Applications



TK CouchDB cluster



