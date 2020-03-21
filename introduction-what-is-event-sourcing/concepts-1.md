# Concepts

## Events

An event is something that happened.

TK examples

{% hint style="info" %}
"Event" is a bad name for this concept. A better name would be "fact" or "[historical fact](https://speakerdeck.com/npryce/mistakes-we-made-adopting-event-sourcing-and-how-we-recovered?slide=13)".
{% endhint %}

## Event Sourcing

Your state is built from events. The event stream is the source of truth.

## Commands

A command is something you want to happen. It can be rejected, for example, when you don't have permission. After a command is accepted, it can result in one or more events.

TK examples

{% hint style="info" %}
_Command_ is a bad name for this concept. A better name would be _request_: I want something to happen, so I _request_ it. This captures an important semantic, since your command can be denied. _Command_ seems to imply that you are commanded or forced to carry out the instruction: you must do it. That's not the case. If you're not authorised, or what you're requesting doesn't make sense, your command can be rejected.
{% endhint %}

## Projectors

## Write Models & Read Models

## Event Store

A database in which you can store events.

TK what kind of databases can be used - what databases are best - what conveniences do dedicated event stores provide

## Event Stream

## Aggregate

## Snapshot

## Side Effect

## Event Sourcing, Event-Driven, Event-Emitting

### Event Sourcing

Your state can be built from events.

### Event-driven

An event-driven architecture emits Domain Events

Example: A CI system emits an event when the build fails.

### Further reading

* [https://www.innoq.com/de/blog/domain-events-versus-event-sourcing/](https://www.innoq.com/de/blog/domain-events-versus-event-sourcing/)
* [https://verraes.net/2019/08/eventsourcing-state-from-events-vs-events-as-state/](https://verraes.net/2019/08/eventsourcing-state-from-events-vs-events-as-state/)



