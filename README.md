# FT_MALLOC
## DESIGN
Philosophers is a solution to the [Dining Philosophers Problem](https://en.wikipedia.org/wiki/Dining_philosophers_problem), an example problem created by Edsger Djikstra (refined by Tony Hoare) to illustrate problems in managing resource access among concurrent processes. Our solution utilizes an asymmtrical solution: resources have a partial ordering imposed on them, and even numbered philosophers acquire their lower ordered mutex before the higher ordered mutex, while the odd numbered philosophers acquire their mutexes in the reverse order. Mutexes are released higher first, then lower. While rarely running the risk of resource starvation, this solution provides philosophers relatively equal access to resources with a limited number of synchronization primitives (*pthread_mutex_lock*, *pthread_mutex_unlock*, *pthread_create*, and *pthread_join*). 

## REQUIREMENTS
Our program assumes that *make*, *ncurses* and *pthreads* are both installed and available on the system.

## USAGE

The *eating*, *resting*, and  *feeding*,times of the philosopers are controlled by the macros `TIME_EAT`, `TIME_REST`, `TIME_THINK` inside `includes/philo.h`. Altering these values will change the behavior of the philosophers. 
```
# Compile the program
$ make
# Execution
$ ./philo
```

## RESOURCES
- [Dining philosophers problem](https://en.wikipedia.org/wiki/Dining_philosophers_problem)
- [CS170 Lecture notes -- Dining Philosophers](https://sites.cs.ucsb.edu/~rich/class/cs170/notes/DiningPhil/index.html)
- [ThreadMentor: The Dining Philosophers Problem: The Lefty-Righty Version](https://pages.mtu.edu/~shene/NSF-3/e-Book/MUTEX/TM-example-left-right.html)

