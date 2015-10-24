### Usage

Start the mailbox application to receive requests

```
$ cargo run
```

When the application runs successfully we are now able to send messages via the `netcat` tool or `telnet` on Windows.

```
$ nc 127.0.0.1 7200
A Message
```

This starts netcat and sends the given string to the mailbox app.
Then to fetch the message run `netcat` again and send `READ` message.

```
$ nc 127.0.0.1 7200
READ
```

This consumes and displays the previous message. But the approach when using `Mailbox` has a few drawbacks,
especially if several different clients try to send messages at the same time or want to access the content of the previous message.
