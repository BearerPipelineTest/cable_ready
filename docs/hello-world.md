---
description: Minimum Viable CableReady.
---

# Hello World

One of the most powerful and creatively interesting features of CableReady is that it can be called from [any](cableready-everywhere.md) part of your Rails application. And thanks to the new [`stream_from`](stream_from.md) feature in CableReady v5, you can use it without any client configuration.

Just use a `stream_from` helper in your template wherever you need [Reactive](https://obie.medium.com/react-is-dead-long-live-reactive-rails-long-live-stimulusreflex-and-viewcomponent-cd061e2b0fe2) functionality:

```text
<%= stream_from :foo %>
What does the agnostic, dyslexic insomniac do? 
```

Everyone looking at this page - or any other page which is subscribed to `:foo` - will instantly see an update when the following Ruby code executes:

```ruby
cable_ready[:foo]
  .append("body", html: "They lay awake, wondering if there is a dog.")
  .broadcast
```

You just ran code on the server that dynamically updated text on potentially thousands of clients, without writing any JavaScript.

![Jazz Hands](.gitbook/assets/eunji.gif)

You could, in theory at least, be done learning CableReady and just start using its [35 operations](reference/operations/) in your controllers, models, Reflexes and jobs. What a time to be alive! ✨

However, most developers will want to keep reading and learn how to use Channels.
