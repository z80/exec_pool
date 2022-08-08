# ExecPool

Gd-script ExecPool is made for asyncronous task execution.

You can limit number of threads it uses. The value is located in the resource file "res://addons/exec_pool/exec_pool_settings.tres" **max_threads_qty**. If the number is 0 or negative, *OS.get_processors_numer() - 1* is used.

## Typical usage

There are two options.

1) Add **ExecPool** node to your scene tree.
2) Or add **ExecPool** creation to "Project->Project Settings->AutoLoad".

There are 3 methods:

1) ExecPool::start( object: Object, method_name: String, callback_name: String )
2) ExecPool::start_with_arg( object: Object, method_name: String, callback_name: String, argument )
3) ExecPool::start_with_args( object: Object, method_name: String, callback_name: String, arguments: Array )

for calling a method *method_name* in the *object*. After the *method_name* returns, the *callback_name* is called with the result returned by *method_name*. *start_with_arg* calls mathod *method_name* with an argument. "start_with_args" calls method *method_name* with an array of arguments. 

See **res://addons/exec_pool/examples/exec_pool_example.tscn** for a usage example.

