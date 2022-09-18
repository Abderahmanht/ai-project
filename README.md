created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# SMART ROCKETS WITH DNA

Final project for the Building AI course

## Summary

The project i want to present is a genetic algorithm for a population that tries to reach a target for generations


## Background
This project doesn't really solve real world problems, but i learned quite a few things : 
* Fitness, fitness is probably the most interesting thing in a genetic algorithm, it solves the problem of how to know if a member of the population is doing well.
* Awards, altough this project doesn't really use an award and punishment system, but it does increase or decrase the fitness based on how the member is performing.
* Curiosity, Haha this is the main problem, it solves my curiosity, seeing the creatures behave and think on their own is fascinating 


## How is it used?

it is mainly used to see, study, and try to understand how the members behave based on their fitness values, mutations, DNA..


This is done is P5.js, a Cool JavaScript Library.

Below is the Rocket function, the rocket is the member of the population, it has a position,velocity,acceleration ... and a calculate fitness method.
The fitness is calculated by mapping the distance of the rocket to the target, it means that the closer it gets, the more fit it will become.
If it crashes (on a wall or on the edges of the canvas (HTML canvas), they die and their fitness value is divided by a value.
```
function Rocket(dna){
  this.pos = createVector(width / 2, height);
  this.vel = createVector();
  this.acc = createVector();
  this.completed = false;
  this.crashed = false;
  this.name = random(name);
  this.Race = [];
  this.Race = new DNA();
  if(dna) {
    this.dna = dna;
  } else {
      this.dna = new DNA();
  }
  
  
  this.fitness = 0;

  this.applyForce = function (force) {
    this.acc.add(force);
  }
  
  
  this.calcFitness = function() {
    var d = dist(this.pos.x, this.pos.y, target.x,target.y);
    this.fitness = map(d,0,width,width,0);
    if(this.completed){
     this.fitness *= 15;
     let completed = createP(counter + ' REACHED THE TARGET, Name : ' + this.name).style('font-    family','tahoma');
      completed.style('color','green');
      counter+=1;
    }
    if(this.crashed) {
      this.fitness /= 10;
    }
  }
```
![image of the rockets trying to reach the white ellipse (target) ... Their only purpose in life ..](/Capture.JPG)

If you want to look at the entire code, here's is the link : https://codepen.io/abderrahmane-el-hathout/pen/OJZPvJp


## Data sources and AI methods

The data is stored on arrays, or objects, no external data is necessary here.

## Challenges

I would say it doesn't really solve the survival life evolution, i would like to learn how i can code an entire survival evolution life simulator, that would use collaborations, making allies and enemies, kill, build homes, develop strategies... ect

## What next?

Just like i mentioned in Challenges, an evolved system, and i will probably need at least one ML expert for that ;( (and a designer lol)


## Acknowledgments

* THE CODING TRAIN !! He's the best, i've only changed a few things but the project is his.
