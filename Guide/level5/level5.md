![alt text](image.png)

so now we are at level 5;

**Theory and new concepts**

# Routing Tables: 
A "cheat sheet" that tells a device exactly which local router to hand data to when the destination is outside its network.

# Default Route
 (default => IP): The catch-all rule. "If I don't know where this goes, just send it to this IP."

# Static Route
 (Network => IP): A specific rule. "If data is going to this exact network, send it to this specific IP."

# The Golden Rule:
 The "Next Hop" IP (the right side of the arrow) must be inside the sender's local subnet. You cannot hand a packet to a router you cannot locally reach.


 so here we have a static ip for r2 and for r1 
 we see that host b1 is connected with interface r2 so they need to be in the same subnet mask 
 also we have that the netwrok ip the first 3 part of the ip ned to be the same 

 now we have machine of host B we dont know where the data is going so just sent it to r2

 now host a has to have the same subnet mask as r1 so 
 and now u can calculate the ip urself 

 so now we have machine A what is it trying to do its trying to sent data to the machine B thats why after the => we choose the ip of R1 so it can sent back the data but what to do prior that :

 **now for the other one we just choose default why??**
**a funny way to get this is**
Imagine you are standing in a house that only has one front door leading to the outside world.

Do you need a giant, specific map taped to the inside of your door detailing the exact coordinates of the grocery store, the bank, and the post office?

No. Because no matter where you are going, your first step is always exactly the same: walk out that one front door.

so it figures itself where to go .

![alt text](image-1.png)