# Project Management

## Learning Resources

- [Engineer Manager](https://github.com/ryanburgess/engineer-manager)
- [The Agile Samurai](https://pragprog.com/book/jtrap/the-agile-samurai)

## Tools

- [meistertask](https://www.meistertask.com/)
- [Wrike](https://www.wrike.com/)


## Book: The Mythical Man-Month

* “All programmers are optimists. Perhaps this modern sorcery especially attracts those who believe in happy endings and fairy godmothers. “

* “ This time it will surely run “ or “ I just found the last bug”

* Book the mind of the maker – Dorothy Sayers

* “ Adding manpower to a late software project makes it later” – Brook’s Law

* 1 man per independent task

* People aren’t too efficient on communication

* Hence tasks that require a high level of communication will cause poor quality and that will make it slower.

* Building a large software project is like building a cathedral. You end up with different arched trace styles \(mash up\)

* Why did the bible tower fail?

* Lack of good communication

* Software easy underestimate time by half.

* “Good cooking takes time. If you are made to wait , it is to serve you better and to please you”

* Menu of restaurant Antoine

* The architect designs but should leave the implementation details to the builder, so it doesn’t kills the builder inventiveness.


### When estimating include:

* Programming

* Debugging

* Machine downtime

* Higher-priority short unrelated jobs

* Meetings

* Paper work

* Company business

* Personal time

* Sickness

* Corrections


### more notes

* The more interactions between programmers the less productivity will be

* Systems program building is an entropy- decreasing process , hence inherently metastable program maintenance is an entropy-increasing process, and even its most skillful execution only delays the subsidence of the system into …

* Successive releases in a large operating system the total number of modules increases linearly with release number, but that the number of modules affected increases experimentally with release number. All repairs tend to destroy the structure , to increase the  entropy and disorder of the system less and less effort is spent on fixing original design flaws more and more is spent on fixing flaws introduced by earlier fixes. As time passes the system becomes less and less well ordered. Sooner or later the fixing ceases to gain any ground. Each forward step is matched by a backward one. Although in principle usable forever the system has worn out as a base for progress. Furthermore, machines change configurations changes and user requirements change, so the system is not in fact usable forever. A brand-new, from – the –ground-up redesign is necessary.

* Belady and Lehman “things are always at their best in the beginning “

* “That is the key to history. Terrific” energy is expended – civilizations are built up – excellent institutions devised; but each time something goes wrong. Some fatal flaw always brings the selfish and cruel people to the top, and then it all slides back into misery and ruin. In fact, the machine conks. It seems to start up all right and ruins a few yards and then it breaks down. “ – Pascal C.S. Lewis

* Each master mechanic has his own personal tool set , collected over a lifetime and carefully locked and guarded- the visible evidence of personal dumps, disk space utilities etc , stashed away in his file. This is foolish for a programming project. First, the essential problem is communication and individualized tools hamper rather than aid communication. Second, the technology changes when one changes machines or working language, so tool lifetime is short. Finally, it is obviously much more efficient to have common development and maintenance of the general – purpose programming tools.

* The modern magic “ I can write programs that control air traffic, intercept ballistic missiles, reconcile bank accounts, control production lines.”

* The estimated dates are the property of the lowest level manager who has confidence over the piece of work in question.

* The project manager has to keep his fingers off the estimated dates, and put the emphasis on getting accurate, unbiased estimates rather than palatable optimistic estimate or self-protective conservative ones.

- spreadsheets + simple database systems

### Productivity software
- writing
- drawing
- file
- spreadsheet
- generalized math & statistical packages
- simple programming capabilities

> The most important function that software builders do for their clients is the interactive extraction and refinement of the product requirements. The clients do not know what they want. Complex software systems are moreover, things that act, move, that work. The dynamics of that action are hard to imagine. So in planning any software activity, it is necessary to allow for an extensive iteration between the client and the designer as part of the system definition.

- Growing software instead of building or writing.

### On OOP

> Unfortunately the self-same strong type-checking in C++ that helps programmers to avoid errors also makes it hard to build big things out of little ones.

### On Reuse

> Doing it requires both good design and very good documentation.

- Rule of thumb: Reusable components will take twice the effort of a one-shot component.
- Reusable modules offered between 1% - 20% of the normal development cost.
- The higher the level at which one thinks, the more numerous the primitive thought-elements one has to deal with.
- Every time we reuse, we are radically raising the sizes of our programming vocabularies.
- Vocabulary learning constitutes no small part of the intellectual barrier to reuse.


### Programming languages

- Programming languages are much more complex than machine languages
- Natural languages are more complex still.
- Higher level languages have larger vocabularies, more complex syntax and richer semantics.
- 3000 API methods, many with 10 to 20 parameters and options.
- To program with a library you must learn the API and functional behavior to achieve all of the potential reuse
- This is hopeless. Native speakers routinely use vocabularies of 10,000 words.
- People learn in sentence contexts. That's why we need to publish many examples in the docs.
- People only memorize spelling. They learn syntax and semantics incrementally, in context, by use.
- That's when REPL, fiddles and tutorials come useful.

### Conceptual Integrity

> A clean, elegant programming product must present to each of its users a coherent mental model of the application, of strategies for doing the app, and of the user-interface tactics to be used in specifying actions and parameters.

- Most purely intellectual works such as books, musical composition and elegant software products are designed by a single mind or by a pair.
- Any product that is sufficiently big or urgent to require the effort of many minds has to have an outcome conceptually coherent to the single  mind of a user and at the same time designed by  many minds.

- Break big projects into sub projects with defined boundaries
- Avoid overloading a product with features of marginal utility at the expense of performance or ease of use.



