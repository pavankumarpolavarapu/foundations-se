### The Alternative Principles: BASE

If ACID is like a pessimistic, strict accountant, BASE is like an optimistic, flexible event coordinator.

**BASE** is an acronym that describes the properties of these highly available systems:

#### BA - Basically Available

*   **What it is:** The system guarantees availability, as described in the CAP theorem.
*   **In Plain English:** **The system is always on.** It will always respond to a request. It might respond with slightly old data, or it might respond with "I'm working on it," but it won't give you an error just because it's busy syncing.
*   **Analogy:** You ask Instagram for the "like" count on a photo. It will *always* give you a number. It won't freeze or crash just because the absolute latest "like" from a server in Australia hasn't arrived yet. It gives you the best answer it has right now.

---

#### S - Soft State

*   **What it is:** The state of the system may change over time, even without new input, because of the eventual consistency model.
*   **In Plain English:** **The data is in flux.** Because data is being synchronized across a distributed network, the value you read right now might change on its own a second later as it receives updates from other nodes. The state is "soft" until it settles.
*   **Analogy:** You're at a huge concert and you ask a security guard how many people are inside. He says "about 50,000." You ask another guard a minute later, and he says "about 50,100" because he just got an update from the main gate. The state of "how many people are inside" is soft and constantly updating in the background.

---

#### E - Eventual Consistency

*   **What it is:** If no new updates are made to a given item, eventually, all accesses to that item will return the last updated value.
*   **In Plain English:** **It will all sync up... eventually.** This is the big one. It doesn't promise *immediate* consistency, but it promises that if you wait long enough, all the servers will agree on the final state. "Eventually" for most modern systems is on the order of milliseconds, but the guarantee is not for "right now."
*   **Analogy:** You update your profile picture on Facebook. Your friend in your same city sees it instantly. Your cousin in another country might see the old picture for another 5 seconds. But *eventually*, everyone, everywhere, will see the new picture. The system has become consistent.