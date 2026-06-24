# modules-div
A Eurorack Clock/Frequency Module - based on a TP4040BE

I have some idea in mind, for which I need a clock divider. For sure, there is Doepfer's A-160 (https://doepfer.de/a160.htm) which would do the trick, but why not building something on my own? 

I have a couple TP4040BE chips here. These are binary counters, so they have one `input` and one 
`reset-input` and a couple of outputs `q1`, `q2`, ...
In addition, they store internally a `counter` and the outputs show a binary representation of that counter. Each time a signal on `input` is detected, the `counter`is incremented by one. This leads to the following output sequence (`q1`, `q2`, ...):

* (0,0,0,0,0,...)
* (1,0,0,0,0,...)
* (0,1,0,0,0,...)
* (1,1,0,0,0,...)
* (0,0,1,0,0,...)
* (1,0,1,0,0,...)
...

So each output changes twice as slow as the one before. For this, they are quite fine to create a clock or frequency divider.



# References: 

* hagiwo's 6$ Clock Divider Module: https://note.com/solder_state/n/n991254a0f20a?hl=en
* a youtube video on this: https://note.com/solder_state/n/n991254a0f20a?hl=en
* hagiwo's patreon: https://www.patreon.com/hagiwo
* benji's miniDiv Clock Divider Module: https://benjiaomodular.com/post/2023-09-11-minidiv/
* a youtube video on this: https://www.youtube.com/watch?v=msd9dFOPEkw,
* a way to sponsor benji a coffee: https://ko-fi.com/C0C24WFYS
*  Eddy Bergman's clock divider:  https://www.eddybergman.com/2025/01/Clock-Divider.html
