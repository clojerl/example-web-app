# Example web application

This is a very simple web application that shows how to set up a
Clojerl project at this very early stages.

It uses the `rebar3_clojerl` plugin to compile and to bring up a REPL.

## Quickstart with Docker Compose

    docker-compose up

This will start the application on port 8080. To use the REPL, use
`docker-compose run`.

    docker-compose run --rm server rebar3 clojerl repl

## Build

    git clone https://github.com/clojerl/example-web-app
    cd example-web-app
    rebar3 clojerl compile

To start the REPL just run:

    rebar3 clojerl repl
    ===> Verifying dependencies...
    ===> Compiling web-app
    Clojure 0.0.0-988.b107f25
    clje.user=>

Now we can start the `web-app` application:

    clje.user=> (application/ensure_all_started :web-app)
    #erl[:ok #erl(:ranch :cowlib :cowboy :web-app)]
    clje.user=>

You should see a `Hello World!` when browsing to
`http://localhost:8080`.

## Playing around in the REPL

Changing the message shown is as easy as redefining the `message` var
in the `web-app.root` namespace.

    clje.user=> (ns web-app.root)
    nil
    web-app.root=> (def message "Hello Universe!")
    #'web-app.root/message
