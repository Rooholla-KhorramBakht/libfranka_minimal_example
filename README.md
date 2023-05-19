# Libfranka Minimal Example 

This is a minimal C++ example using libfranka library for communicating with Franka FR3 robots. 

## Compilation
Clone the current repository and run the following to compile the example.
```bash
cd libfranka_minimal_example
mkdir build 
cd build
cmake ..
make
```
## Running the Example
```bash
cd build
./pose_example <robot_ip_address> 
```