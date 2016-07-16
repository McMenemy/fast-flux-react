# fast-flux-react

## docs
require at top of component you want to use

ex/ var FastFlux = require('../util/fast-flux-react/fastFlux')

then do FastFlux.webCycle(method, url, options)
    method: the HTTP method you want to use all lowercase ('put', 'post', or 'get')
    url: the back end route you want to hit
    options: an object of different options which are defined below
        body: object (data to be sent in AJAX, required for post and put requests)
        success: function    (optional front end successCallback)
        error: function      (optional front end errorCallback)
        shouldReceive: boolean  (if the backend data should end up in a store)
        type: the name of the store action that received data (required if shouldReceive is true)

 example
 var signUpBody = {
   username: this.state.username,
   password: this.state.password,
   email: this.state.email,
 };
 FastFlux.webCycle('post', '/signup', {
   body: signUpBody,
 });
