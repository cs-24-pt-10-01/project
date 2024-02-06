# project

## RAPL measure library

The idea is to combine features of existing library solutions, e.g. pyRAPL (decoration of functions), jRAPL (sampling rate), and utilize this to perform RAPL measurements for languages that does not feature it yet (JavaScript, PHP, Go ...). This is very easily possible because of the DLL, especially for [PHP](https://stackoverflow.com/a/41856309). Using the DLL still makes the process of using it on either Linux or Windows, or Intel or AMD trivial. However, the energy joules should likely be converted in the library itself, and not in Python (as we did before...).

Logging could be two-fold (or more?). The default way currently is to utilize a CSV file or a log file, but this means that in the case of a prod environment, the file is stored on that machine. An additional approach is to utilize a server (preferrably TCP/UDP, no HTTP, cause performance), where the DLL either acts like a client or a server (preferrably client since likely only need one connection and to minimize overhead). This could push towards enabling profiling, in the sense that the machine that runs the code and measures energy will send relevant data back to the profiler, which can be used to understand how well the energy consumption is on the machine currently being used. Assuming multiple developers would like to see profiling data at the same time, this means however that the DLL must act as a server, and not a client.

Contributions:
- A flexible library implementation that enables writing additional libraries for multiple languages to use it. It enables not only Linux (as seen in all libraries), but also Windows, along with AMD. It is a modular, single-implementation solution.
- 
