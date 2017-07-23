PINIT is yet another init system. This time in python.

FAQ:

Q: Why should I use this?

A: You shouldn't. Ever. Seriously

Q: Is this stable for production?

A: No

Q: Why would you write an init system in python?

A: It is simple for people to understand. An init system is normally shrouded in mystery and I wanted to show how simple it was in something easy to read.

Q: Why create one this simple?

A: An init system needs to do 2 things. Get the system up safely, and shut down safely. That's all.

Q: How is this better than what I'm running?

A: Most init systems, and definately the most popular ones, try to handle everything. It seems like a smart idea, until something goes wrong.

Q: How do I start/configure/stop services?

A: That's up to your service manager. Please consult their manual.

Q: Why not include a service manager?

A: It is pretty simple. This is an init system, not a service manager. Feel free to plug one in as it will start one at boot, and turn it off when powering down/rebooting.

Q: Why not use systemd? That's been around for ages now and everyone is using it. It works great!

A: http://without-systemd.org/wiki/index.php/Arguments_against_systemd

Q: So I understand all of the problems there, but how can we fix them?

A: I'm not always correct, but I personally believe, like many others, that we need to seperate the tools into things that are easier to maintain, and switch out. I can't switch out the init systemd if I want the service manager. You lose choice when systemd does one thing you like even though many things it does well.

Q: So we just have to re-write everything?

A: No. We have a lot of projects that we can fall back on. Systemd is the big hitter, but it's not the only one around.

Q: So why all of the systemd hate and a useless init system if you won't fix it?

A: I wrote a refrence init system so people can understand what it is, and I am planning on writing a refrence syrvice manager in the near future.


Now that you've read through the whole Q&A, you may see why I started this. I personally love systemd's service manager. I love the config files. I hated the old init bash scripting nonsense, and think it was a great idea that just went wrong. Systemd has become hard to maintain, and has made some serious decisions that I and many others don't agree with and have tried to merge many of the tools, which tightens it's grip on the market. I propose having a new service manager that is inspired by systemd, but with new goals. It needs to not absorb everything, and needs to not be responsible for the init process. It needs to be able to not be so hard to change out, but still give us the ability to use systemd config files as close as possible (but not the 0day username issue of course). That would allow us to easy swap it out in production systems with little effort, while massively reducing the stranglehold of systemd and their abused power on the userbase. Those are the new goals for the new service manager, and it should be able to be launched from this very simple init system.
