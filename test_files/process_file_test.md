This is a very basic literate file as an initial test.

###### file:process_file_test.js
    (function () {
        ###### shared state
        ###### functions
        ###### api
        // This shouldn't be detected as a macro:
        // \###### not a macro
    }());


This seems pretty typical of JavaScript.

###### shared state
```javascript
var _state = 'off';
```

###### functions

    function toggle_state() {
        if (_state == 'off') {
            _state == 'on';
        } else {
            _state == 'off';
        }
    }

    function get_state() {
        return _state;
    }


This is an example of why a literate program is really nice. I can add to the
shared state at the same time as I add a function to manage it.

###### shared state
    var _message = '';

###### functions
```javascript
function set_message(message) {
    _message = message;
}

function get_message() {
    return _message;
}
```


Now we can provide an API to users of this library.

###### api
    window.mylibrary = {
        message: get_message,
        state: get_state,
        toggle_state: toggle_state};