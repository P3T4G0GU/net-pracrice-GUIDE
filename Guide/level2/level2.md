# Level 2

so as you can see its kinda similar to the first exercise, what you need to do is just fix the B1 mask to `255.255.255.224` since A1 has its mask static.

![alt text](<Screenshot From 2026-05-25 13-51-42.png>)

now lets find whats the range of the usable hosts that you can use:

```
256 - 224 = 32
```

so block 1 is from [0-31] of which 0 and 31 are administrative landmarks,
so the usable host range is from **[1-30]**

next we have block 2: [32-63] of which 32 and 63 are administrative landmarks so usable host range is from **33-62** etc...

so since the usable host range variates by 30, and we have an IP of `192.168.33.222` you can just take the broadcast address - 1 which is **(192.168.33.221)** and its gonna work.

---

next we have hosts C and D

now the mask `255.255.255.252` is the same as saying `/30`

**WHY?**

`255.255.255.252` in binary is:

```
11111111.11111111.11111111.11111100
```

as you can see there are **30 bits that are 1** and **2 bits that are 0** —
thats why `255.255.255.252` is the same as saying `/30`

---

now the real problem here is the IP. why?

`127.x.x.x` is a loopback IP and its just used for testing, you can also call it a localhost IP.

when Computer C tries to send a packet to `127.0.0.4`:

- the computer's OS intercepts the packet before it even touches the network card
- the OS sees the `127.` prefix and says "oh, this is for me" and loops the packet right back into its own memory

**a funny way of putting it:**

> its exactly like writing a letter to your neighbor, but putting your own home address in both the "To" and "From" sections. the mail carrier looks at the destination, turns right around, and drops it back into your own mailbox. the letter never leaves your porch, and your neighbor never sees it.

what you can do instead is create an IP where the first 3 octets are the network part, like:

```
42.42.42.(host)
```

so since the mask is `255.255.255.252`:

```
256 - 252 = 4
```

so we have block 1 from **(0-3)** and 0 and 3 are administrative landmarks, so usable hosts are **1 and 2**

so you can assign:
- `42.42.42.1` → Host C
- `42.42.42.2` → Host D

![alt text](<Screenshot From 2026-05-25 14-30-27.png>)