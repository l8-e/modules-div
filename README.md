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

## On the shoulders of giants
Doing a quick research, the usual suspects did what I plan before I started to think about this: hagiwo has buit a 6$ clock divider based on that very chip and benji did improve it, adding even an internal clock signal. Also Eddi Bergman has schematics online how to built such a clock divider. So I could simply copy what they did, not thinking about it and .. be happy... but, i want to understand how it works, so I redo their work and see what I will come up with. 

First, I only whant to have one output and want it to be switchable to a divider factor from 1/2, 1/4, ... 1/256. I have no 8 step rotation switch, so I use a dip switch in stead. Also I am quite curious what will happen if i activate more than one of the outputs. 

So my first schematics is very basic. 


# References: 

* hagiwo's 6$ Clock Divider Module: https://note.com/solder_state/n/n991254a0f20a?hl=en
* a youtube video on this: https://note.com/solder_state/n/n991254a0f20a?hl=en
* hagiwo's patreon: https://www.patreon.com/hagiwo
* benji's miniDiv Clock Divider Module: https://benjiaomodular.com/post/2023-09-11-minidiv/
* a youtube video on this: https://www.youtube.com/watch?v=msd9dFOPEkw,
* a way to sponsor benji a coffee: https://ko-fi.com/C0C24WFYS
*  Eddy Bergman's clock divider:  https://www.eddybergman.com/2025/01/Clock-Divider.html
