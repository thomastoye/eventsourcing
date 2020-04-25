# Advantages of Event Sourcing

## Maps Mental Model

Events map closely to the mental model of the domain you're working in. `AudioMessageSent` is clearer than _add a new row to the `messages` table with the `audio` column set to `TRUE`._

## You Don't Lose Any Data

Since your event store is append-only, you can't accidentally delete your `users` table. But you also don't lose things you don't deem important at the moment.

Often, the business will come to you with a question like "How many tenants switched their plan last year?", and your reply is "Well, we update that in-place, so we don't really know." With Event Sourcing, this could be as easy as filtering your events table for `TenantSwitchPlan` events.

## Audit Log For Free

An audit log is one of the things you'll need when you want to make your product [enterprise ready](https://www.enterpriseready.io/features/audit-log/) or compliant. An event sourced system makes this easy - your event stream, by definition, contains all actions that happened in your system.

{% hint style="warning" %}
Note that some domains may require you to store more than just state-changing events. For example, a electronic health record management system may need to log at which patients' charts a nurse looks.
{% endhint %}

## Debugging Is Great Again

TK but harder if you have a lot of events

{% hint style="info" %}
A client emailed me. The attendances in a report did not add up! Using the event stream, I could tell them who added and removed people from the attendance list, on what date and with what account. They were thrilled with the detail I could provide them with and quickly concluded the report was correct, but they data they had fed the system was incorrect.
{% endhint %}

## Goodbye ORM mismatch

TK just create a new read model

The choice of a data store is very important in non-event sourced project. Different products are better suited to different domains. When using event sourcing, you can just hydrate a new database from the log. In a company where I interned, we processed IoT sensor data. We would send a new event to MongoDB for short-term caching, to ElasticSearch for metadata searching, and to KairosDB for graphing time series. Use the right tool for the job, and don't Frankenstein your Postgres installation by shoehorning all kinds of extensions on it.

## Time Travel

## Offline and Offline-first Applications



TK CouchDB cluster



