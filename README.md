# Static + dynamic library link = error
Using the command `dub build`

Compiling a shared library that uses code from a static library results in a linker error, namely

(with DMD)
```
relocation R_X86_64_32 against symbol `__dmd_personality_v0' can not be used when making a shared object; recompile with -fPIC
```

and

(with LDC)
```
relocation R_X86_64_32S against hidden symbol `ldc.dso_initialized' can not be used when making a shared object
```

and

(with GDC, probably not related)
```
fatal error: -fuse-linker-plugin, but liblto_plugin.so not found
```
Linking is confirmed to fail on Arch Linux 64bit, with DMD, LDC and GDC.

The "inspiration" for this was the ["distort" example in dplug](https://github.com/AuburnSounds/dplug/tree/master/examples/distort)
