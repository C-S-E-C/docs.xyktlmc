# Starting Server Bugs  
This passage will tell you how to solve some regular problems that may happen while starting the server  
  
  
## Problem 1:  
When a player wants to join the server the launcher says:  `Name not resolved`  
This means that when the launcher tried to find the dns record of the server, it faild.  
### Causes & Solutions:  
1. The dns record is missing.  
    - log into cloudflare try to find a `SRV` record if you failed to find on that means that you fhave found the cause!  
    - How to make a `SRV` record  
       1. Click on create a record  
       2. Set the Type of the record to `SRV`  
       3. In the name section write: `_minecraft._tcp.`+the name of the sub-domain ex. for mc.example.com write `_minecraft._tcp.mc`. If you dont want to use a sub-domain write `_minecraft._tcp`  
       4. Now set the `Priority` and  `Weight` to `0` and set `TTL` to `Auto`  
       5. Login to the frp provider like `frp.cool` click on the tunnel details. If you dont have a tunnel head towards `Problem 2 Cause 3`  
       6. Copy the `Remote Port` (in frp) to `Port`(in Cloudflare)  
       7. Copy the `Server IP` (in frp) to `Target`(in Cloudflare)  
       8. Click Save  
2. You have no WIFI  
    - Fuckin' connect to the goddamn WIFI  
  
  
## Problem 2:  
When a player wants to join the server the launcher says:  `get sock opt`  
This means that the FRP isn't running correctly  
 
