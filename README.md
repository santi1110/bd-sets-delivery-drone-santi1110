## Fix your Delivery Drone Fleet

Amazon Fresh is adding a new service that offers fresh fruit delivery. A drone picks fruit fresh from the tree or vine
and flies it straight from the orchard to the hungry customer who ordered it.

You are working on the system that manages the fleet of drones used for this service. Every drone in the fleet is
assigned a registration number by a local jurisdiction. You are going to try to address three different issues your
team is facing:

### Issue 1 - Performance
As the fleet has expanded to tens of thousands of drones, there have been performance issues adding and removing
drones from the fleet system. 

### Issue 2 - Duplicate Drones
There have been bugs related to duplicate drone information in the fleet.

### Issue 3 - Checking for Drones from a specific location
You are also adding a feature that checks whether the fleet contains any drone from a particular location. This will
help enable features that the legal team needs to deal with drone licensing audits from various cities and countries.

## Getting familiar with `DroneFleet` and `DeliveryDrone` code

Let's start by reading through the `DroneFleet` and `DeliveryDrone` source code.

You'll note that the `DeliveryDrone` class includes a `registrationNumber` attribute representing the registration id
for this drone. It also includes a `locationCode` which is a code identifying the jurisdiction where this
drone is registered. Every combination of `locationCode` and `registrationNumber` are globally unique -- they identify 
a single drone.

The `DroneFleet` contains any number of `DeliveryDrone` objects. Later our team will be adding more business logic to
this class, but right now it is basically a wrapper around a collection of `DeliveryDrone` objects, supporting simple
operations such as `addDrone()`.

## Tackling performance and duplicate drones

Let's focus on the first two issues - performance and duplicate drones. Modify the `DroneFleet` and `DeliveryDrone`
classes so that our drone fleet can't contain drones with the same `registrationNumber` from the same `locationCode`.
The changes you make should also address the performance issue we are experiencing. We should be able to add and remove
drones from the fleet in constant time. That means we'll be
testing your implementation of `addDrone` and `removeDrone`. You shouldn't yet touch `containsDroneFromLocation`, but
the rest of the code is free game!

Once you're ready to see if your `addDrone` and `removeDrone` methods are working as expected, run
the tests in `DroneFleetTest`

**HINT:**
[I changed the type of `drones` but my remove and add tests are still failing.](hints/hint-02.md)

HINT:
[I can't find `DeliveryDrone`s implementation of `equals` to fix.](hints/hint-03.md)

HINT:
[I made sure to define equivalency rules for `DeliveryDrones` but my remove and add tests are STILL failing.](hints/hint-04.md)


## Checking for Drones from a specific location

Now let's work on issue 3, implementing the new functionality! The method header has already been created for this
functionality in `DroneFleet`. Read through the `containsDroneFromLocation` JavaDoc in `DroneFleet` and fill in the
implementation for the method.

Once you're ready to see if your `containsDroneFromLocation` method os working as expected, run
the tests in `DroneFleetContainsTest`

**HINT:**
- [containsDroneFromLocation tests fail](hints/hint-01.md)
