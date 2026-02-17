# ft_irc

ft_irc is a project aimed at recreating a simplified IRC (Internet Relay Chat) server in C++.
An IRC server is a text-based communication server that allows multiple users to connect, join channels, and exchange messages in real time (similar in concept to applications like Discord, but purely text-based and protocol-driven).

This project focuses only on the server-side implementation.
Any standard IRC client can be used to connect to the server, such as:

- Irssi (reference client for this project)
- Hexchat 
- Any other IRC client......

## Technical specification
- The project is strictly developed using the C++98 standard.
- The server is implemented using BSD sockets.
- I/O operations are fully non-blocking.
- epoll is used to efficiently manage multiple simultaneous client connections.
- Forking is strictly prohibited. The server must handle all clients within a single process.
## The features
Connection & Authentication
- Clients must provide a password to connect.
- Multiple users can connect simultaneously.

Messaging
- Users can send private messages to each other.
- Users can send messages within channels.

Channels, users can:
- Create channels
- Join existing channels

Channels support configurable modes:
- i = Invite-only channel
- t = Restriction of the TOPIC command to channel operators
- k = Channel password
- o = Channel operator privilege
- l = User limit to channel 

Channel operators (admins) can:
- Kick users
- Invite users to private channels

IRC Commands Implemented :
```
PASS
NICK
USER
JOIN
PRIVMSG
KICK
INVITE
Channel mode handling (+i, +t, +k, +o, +l, -i, -t, -k, ...)
```

## Installation
- Run make
- Execute the program with the password and the port of your choice

```bash
  make
  ./ft_irc [port] [password]
```
    
<div>
    <h3>Language & Tool</h3>
    <p>
        <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c&logoColor=white"/>
        <img src="https://img.shields.io/badge/Make-427819?style=for-the-badge&logo=gnu&logoColor=white"/>
    </p>
</div>
