# Break down task: Each process in one file
 ## breakdown PRD (no code) into large modules (no code).
 ## breakdown large modules (no code) into medium modules (no code)
 ## breakdown medium modules (no code) into small modules (no code). 
 ## breakdown small modules (no code) into tiny modules (no code). 
 ## breakdown tiny modules (no code) into nano modules (no code)

# You dont have to have all 5 breakdown levels. Just make keep in mind the following rules of implementation during the break down process:

## Lowest (smallest) modules have to be reusable 100%*
### from 30-50 tokens
### pure code
### scalable
### reusable (100%)
### can be implemented inline
### independent
                        
## Second lowest modules have to 
### must have less than 300 tokens

## the next one above the second lowest:
### must have less than 2000 tokens

## Always have a feature tracking system that allow to trace 
### dependencies 
### module state: the module has begin, or ended
### sequence of modules
### importance: how important this module overall 