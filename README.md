# commlink-proto

The protocol definition for Commlink, the communication layer at the core of the Decrypt ecosystem.

---

## What is Commlink

Commlink is the nervous system of Decrypt. 

Every signal that moves through the ecosystem, whether from a log watcher, a market tool, or home sensor, will use this language.

Every node in the ecosystem will speak this language. Decrypt will operate in and on this language.

The name comes from the primary communication tool Decrypt uses, an all purpose communication tool called Commlink, set in the Shadowrun universe and cyberpunk in general.

---

## Why it exists

Decrypt is not a collection of tools. It is a person, myself, being built one system at a time, starting with the most fundamental thing a person needs: a way to communicate.

Commlink is that foundation. Before anything in the ecosystem can be useful, the pieces need to speak to each other. Before Decrypt can learn, it needs a language. Before that language can grow, it needs a base to grow from.

This repo is that base. One proto file. The single source of truth that every node in the ecosystem, regardless of language or platform, compiles and builds against.

The protocol is sovereign. Implementations are downstream of it.

---

## How it works

Every signal in the ecosystem is an envelope carrying four things: who sent it, when, how urgent it is, and what it contains.

What it contains is always one of four primitives:

- **Message** - something happened, fire and forget
- **Request** - something happened and a reply is expected
- **Response** - the reply to a request
- **Discovery** - a pattern was found that does not have a name yet

Discovery is the most important one. It is how the ecosystem surfaces what it does not yet understand. The organism notices before it has words for what it noticed.

Signals travel through the Nexus, a central coordinator that maintains a registry of connected nodes, routes signals to subscribers, and buffers anything that has no listener yet. Local nodes communicate via gRPC. Remote and intermittent nodes connect via WebSocket. The envelope is the same either way.

Nodes are self-announcing. Nothing is pre-registered. A node introduces itself, declares what it can send and what it wants to receive, and the Nexus figures out where it fits. The ecosystem self-organizes around what exists.

---

## Design principles

Forward compatibility is the only rule that cannot be broken. The protocol only ever adds. It never removes, renames, or changes the meaning of existing fields. 

Every node that speaks Commlink today will speak it correctly after any future update.

Everything else is downstream of that.

---

## Structure

```
commlink-proto/
└── proto/
    └── commlink.proto
```

---

## Part of the Decrypt ecosystem
Decrypt is the mirror to myself, the person that I was, and the person I became. 
Commlink is how that both Decrypt and I will share that story of who I am and how I got here.
This Proto file is the language that will be used to communicate between Decrypt and the rest of the world.