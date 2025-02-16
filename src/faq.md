# FAQ

## <a name="kernelosdifference"></a> What's the difference between a kernel and an OS?

Sometimes, these terms are interchangeable, however not really ever in free software. In this case the kernel(sometimes in technical docs referred to as the supervisor) manages processes, system calls, coordinates kernel module calls, manages memory, and more. An OS consists of a kernel, a bootloader(sometimes part of the OS or kernel, often not), userspace utilities, init scripts(in the case of aphrodite, an InitEnv configuration, a RamInit script, a DiskInit script, and a SysInit script), userspace utilties, and way more. Something to note is that an OS always includes a kernel and more. Another thing to note for an OS is, as an example, in the case of linux, the most common OS is GNU, which is why [a more accurate name](https://www.gnu.org/gnu/gnu-linux-faq.html) is GNU(the OS)/Linux(the kernel). Similarily, the name that will be used by Aphrodite developers for the kernel is Aphrodite or Aphrokern, and for a full OS (OS name)/Aphrodite. As you can see from this, an OS + kernel combination should generally be called (OS name)/(kernel name).

Tl;dr: A kernel is what runs when you boot up and controls the base level of everything, and an OS includes everything else that is necessary to make a kernel operate. The name used by Aphrodite developers for the kernel is either Aphrodite or Aphrokern, and for an OS (OS name)/Aphrodite.

## <a name="whatis"></a> So what really is Aphrodite?

It is the kernel and a software distribution to make the kernel into a full OS. At the moment, only the kernel exists and is being actively worked on.

## <a name="contributing"></a> How can I help?

Contribute to the codebase! At the moment there isn't a roadmap, but contact @AverseABFun(Arthur Beck) for an idea of what to work on! You can contact them at averse.abfun@gmail.com and they should get back to you within a couple of days. If you are an active contributer, you'll be added to the organization(which at the moment doesn't really do anything for you).

## <a name="teams"></a> Are there teams?

Yes! Currently, as there's only me(Arthur Beck) working on the codebase, there aren't _really_, but there is the infrastructure in place for teams. These teams are:

- Documentation team
- Kernel team

## <a name="philosophy"></a> What's the philosophy of Aphrodite?

- Keep Aphrodite and all official components(projects created and maintained by the Aphrodite team) [free software](https://www.gnu.org/philosophy/free-sw.html) (tl;dr for the link: Free software is software where the users have control to do pretty much whatever they want with it; think of the "free" in "free software" as in "free speech," not as in "free snacks.")
- Prevent something like [what happened to GNU](https://www.gnu.org/gnu/gnu-linux-faq.html) from happening to whatever the main software distribution ends up being.
- Try to prevent memory safety bugs and other bugs that leak data from ever happening (using Rust helps with this).
- Prevent relying on archaic behaviour, however support somewhat old computers.
- NEVER charge money for any official component of Aphrodite.