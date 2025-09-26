# x86_disass
A Disassembler for x86_64 architecture, supporting instruction rewriting, wrote with C&amp;C++

Originally written in C, later on, a C++ API has been introduced. (see at ./uapi/cpp_uapi.hpp)

---
```c++
insn_t in("\xe9\xad\xde\x00\x00");
uint64_t dest = in.PtrAddr(0x55555555050);
// [rip+0xdead] 	-> 0x55555555050+0xdead+<instruction size>
// [rax]          -> -1
in.stick_ptr(0xcafe, ReAsmT::FXD);
in[0]->Value() // ->[rip+0xcafe]
```

view pybind11 bindings for this project - [here](https://github.com/HeX0Rci5T/x86_pybindings)
