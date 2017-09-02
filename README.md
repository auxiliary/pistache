# Pistache

[![Travis Build Status](https://travis-ci.org/oktal/pistache.svg?branch=master)](https://travis-ci.org/oktal/pistache)

Pistache is a modern and elegant HTTP and REST framework for C++.

It is entirely written in pure-C++11 and provides a clear and pleasant API

Full documentation is located at [http://pistache.io](http://pistache.io).

# Fork status
This is a fork from [oktal/pistache](http://github.com/oktal/pistache), with the aim of faster bug fixes/merges. 

So far:

- #117 seems fixed with pull request #118 from [dgreatwood](https://github.com/dgreatwood). 
- #49 is fixed by the fix from [alanbirtles](https://github.com/alanbirtles/pistache)


# Example

## Hello World (server)

```cpp
#include <pistache/endpoint.h>

using namespace Net;

struct HelloHandler : public Http::Handler {
    HTTP_PROTOTYPE(HelloHandler)

    void onRequest(const Http::Request& request, Http::ResponseWriter writer) {
        writer.send(Http::Code::Ok, "Hello, World!");
    }
};

int main() {
    Http::listenAndServe<HelloHandler>("*:9080");
}
```
