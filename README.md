# The 3 Stages of Docker Debugging

**What:** 1.5 - 2hr talk

**Format:** Slides + live demonstrations

**Speaker:** Stephen Lau (@toshi38)

One of the biggest reasons for using Docker is the isolation that it provides.  Unfortunately for many developers working with Docker for the first time, this isolation also changes how they can use the tools they’ve typically used in the past.

With several teams, I’ve observed that they’ve moved through several stages of Docker debugging with varying levels of pain.  To save you this pain we’ll explore each of them with a simple Node.js app.

At the end of the talk, we’ll discuss a little how you can leverage these with other technical stacks.  Links can be provided to the code examples used within the talk.

If you're interested in having this talk delivered please contact Stephen Lau (@toshi38)

## Stage 0: Debug outside of Docker
To begin with most teams run and debug their app locally.  I refer to this as stage 0.  In this part of the talk we’ll set the stage by introducing our demo app, a simple game where a player needs to guess a UUID to win!

## Stage 1: Docker Logs
The first stage of Docker debugging that most developers turn to is the docker logs command.  Developers add console.log() and redeploy the Docker container then collect the logs to debug their application.  This approach is similar to how many developers debugged when they first started coding!

## Stage 2: Open a Port
Many clever developers think to themselves: “Node.js supports remote debugging/inspection, why don’t I use that?”.  They punch a hole in the isolation, leave the required port open and connect the remote debugger.  Perhaps they create a couple of different “profiles” with Docker Compose or a script that allows them to run their containerized app in both debug or non debug mode.

##Stage 3: Docker Networking
Stage 2 solves many of our problems in development, unfortunately we (probably) don’t want to leave ports open or run in debug mode in production.  In addition, if we need to restart our app in debug mode we will lose the current context.  This prevents us from debugging tricky bugs that maybe only show up now and then.  In Stage 3 I will present a method of connecting to an existing running Node.js app without losing the current context.  In order to do this we’ll leverage the Docker networking stack.

