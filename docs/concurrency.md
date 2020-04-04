# The Concurrency Model

## Introduction
To support its concurrency needs. pymata-express divides its workload into
[asyncio tasks.](https://docs.python.org/3/library/asyncio-task.html)

According to [Wikipedia,](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) 
*"concurrency is the ability of different parts or units of a program, algorithm, or 
problem to be executed out-of-order or in partial order, without affecting the final outcome. 
This allows for parallel execution of the concurrent units, which can significantly 
improve overall speed of the execution in multi-processor and multi-core systems."*

Pymata-express consists of two main tasks: 

* Accept and process API calls from the application.
    * Translate the API calls into Firmata formatted messages.
    * Transmit these messages across the serial link.
* Continuously receive data from the serial link while assuring no data loss.
    * Decode the received data.
    * Store information in the pymata-express internal data structures.
    * Notify the application of data change notifications by calling the user-provided callback methods.

If you invoke the keep-alive feature, a third task continuously sends keep-alive messages to
the Arduino.


<br>
<br>

Copyright (C) 2020 Alan Yorinks. All Rights Reserved.
