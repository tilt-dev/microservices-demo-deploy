# Sock Shop : A Microservice Demo Application

WeaveWorks built a great [microservices demo](https://github.com/microservices-demo/microservices-demo)!

We've adapted this demo for Tilt.

## Running the Demo for the First Time:

To see the demo, [install Tilt](https://docs.tilt.dev/install.html) and run

```
$ tilt up
```

## Making a Change to the Frontend

The Tiltfile in this directory is smart enough to check if the front-end repo is
checked out, and if so, builds it from the Dockerfile.

From the current directory, run

```
$ cd ..
$ git clone git@github.com:microservices-demo/front-end
$ cd microservices-demo-deploy
$ tilt up
```

You should see Tilt building the front-end from source.

Tilt will automatically watch all changes to the front-end repo, and rebuild
when it sees changes.

Try making a change to an HTML file. Change "We love socks" to "We adore socks" in
[index.html](https://github.com/microservices-demo/front-end/blob/61d1fdf3ed96a7172e0a2cbaf136d158784f09c0/public/index.html#L86)

Watch as Tilt picks up the change, builds the image, and replaces the existing server.

