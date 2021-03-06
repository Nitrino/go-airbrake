Config
======

set `airbrake.Endpoint` and `airbrake.ApiKey` globals

Methods
=======

`airbrake.Notify(err)` reports an error

`airbrake.Error(err, *http.Request)`can be used to add more context if you are in a http context

You can also automatically have this library report panics, use this method:

`airbrake.CapturePanic(*http.Request)`

example:

````golang
  func serve(w http.ResponseWriter, r *http.Request) {
      defer airbrake.CapturePanic(r)  
      [...]
      panic("Oh no :-(") // will be recorded by airbrake
  }
````
