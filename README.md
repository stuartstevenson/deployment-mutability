# deployment-mutability
Config management has raised a very cool area of thought. Is the application just another part of the systems configuration? Why is the app special and should it be treated differently? I think of the two schools of thought as mutable vs immutable state. Puppet and chef representing the idea that state is mutable and so countermeasures are needed. Docker and containers representing the idea that immutability will remove the need to worry about these problems.

So let's discuss. On a trivial level change and mutability are something that you have to worry about if you expect things to be unmanaged for periods of time. Entropy is the enemy you are fighting, not nefarious agents as we so often use as exemplars.

Immutability shuts down vectors by which entropy shows itself. It also assumes that it is a fight not worth wasting energy on. As you may be gathering I have a preference. Sun Tzu, only fight battles you can win, and all that.

The opposing view is that tools that make you the master of mutability are your friends. You feel more in control as surely you can fight off entropy from your fortress of configuratude. If all config is state, can't functional thinking teach us a thing or two about working with state and sources of truth. 

The Netflix approach of packaging up AMIs with everything they need at build time makes for very reproducible behaviour across environments. Only very external services such as service discovery need to be managed outside of the package. The cons are of course a lack of flexibility.

I feel the trade off is down to the cycle time of your organisation. If you can release changes in hours then rebuilding an immutable package should be a low cost activity. However if releases from commit to production take days then you need to be prepared for other environmental configuration to have changed in that time. And if rebuilding the package isn't feasible due to the length of your delivery pipeline then immutability will be a curse not a boon.
