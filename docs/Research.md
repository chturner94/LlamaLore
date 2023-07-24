```error
llama_print_timings:        load time = 62946.30 ms
llama_print_timings:      sample time =   171.36 ms /   512 runs   (    0.33 ms per token,  2987.86 tokens per second)
llama_print_timings: prompt eval time = 19496.25 ms /   429 tokens (   45.45 ms per token,    22.00 tokens per second)
llama_print_timings:        eval time = 46020.03 ms /   504 runs   (   91.31 ms per token,    10.95 tokens per second)
llama_print_timings:       total time = 65795.20 ms
unexpected fault address 0x0
fatal error: fault
[signal SIGSEGV: segmentation violation code=0x80 addr=0x0 pc=0x470799]

goroutine 1 [running]:
runtime.throw({0x540b96?, 0x79e0?})
        /home/christian/sdk/go1.19.10/src/runtime/panic.go:1047 +0x5d fp=0xc0000749b8 sp=0xc000074988 pc=0x44c2dd
runtime.sigpanic()
        /home/christian/sdk/go1.19.10/src/runtime/signal_unix.go:846 +0x2c5 fp=0xc000074a08 sp=0xc0000749b8 pc=0x4607c5
runtime.(*_type).string(0xbd4ec5d1bf6a69b3)
        /home/christian/sdk/go1.19.10/src/runtime/type.go:55 +0x19 fp=0xc000074a28 sp=0xc000074a08 pc=0x470799
runtime.(*TypeAssertionError).Error(0xc00011a210)
        /home/christian/sdk/go1.19.10/src/runtime/error.go:39 +0x9e fp=0xc000074b30 sp=0xc000074a28 pc=0x420e9e
runtime.preprintpanics(0xc00012e0a0?)
        /home/christian/sdk/go1.19.10/src/runtime/panic.go:581 +0x7f fp=0xc000074b90 sp=0xc000074b30 pc=0x44b13f
panic({0x5325e0, 0xc00011a210})
        /home/christian/sdk/go1.19.10/src/runtime/panic.go:985 +0x3ac fp=0xc000074c50 sp=0xc000074b90 pc=0x44be8c
runtime.panicdottypeE(0xbd4ec5d1bf6a69b3, 0x53ce20, 0x530de0)
        /home/christian/sdk/go1.19.10/src/runtime/iface.go:262 +0x6a fp=0xc000074c70 sp=0xc000074c50 pc=0x4235ea
fmt.newPrinter()
        /home/christian/sdk/go1.19.10/src/fmt/print.go:137 +0x87 fp=0xc000074c98 sp=0xc000074c70 pc=0x49e987
fmt.Fprintf({0x563238, 0xc00012a008}, {0x542195, 0xe}, {0xc000074de8, 0x1, 0x1})
        /home/christian/sdk/go1.19.10/src/fmt/print.go:203 +0x49 fp=0xc000074cf8 sp=0xc000074c98 pc=0x49ec09
fmt.Printf(...)
        /home/christian/sdk/go1.19.10/src/fmt/print.go:213
main.main()
        /home/christian/development/LlamaLore/go-llama.cpp/examples/main.go:58 +0x5b4 fp=0xc000074f80 sp=0xc000074cf8 pc=0x4abc34
runtime.main()
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:250 +0x212 fp=0xc000074fe0 sp=0xc000074f80 pc=0x44eb72
runtime.goexit()
        /home/christian/sdk/go1.19.10/src/runtime/asm_amd64.s:1594 +0x1 fp=0xc000074fe8 sp=0xc000074fe0 pc=0x478581

goroutine 2 [force gc (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:363 +0xd6 fp=0xc000066fb0 sp=0xc000066f90 pc=0x44ef36
runtime.goparkunlock(...)
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:369
runtime.forcegchelper()
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:302 +0xad fp=0xc000066fe0 sp=0xc000066fb0 pc=0x44edcd
runtime.goexit()
        /home/christian/sdk/go1.19.10/src/runtime/asm_amd64.s:1594 +0x1 fp=0xc000066fe8 sp=0xc000066fe0 pc=0x478581
created by runtime.init.6
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:290 +0x25
runtime.(*scavengerState).park(0x5fb800)
        /home/christian/sdk/go1.19.10/src/runtime/mgcscavenge.go:389 +0x53 fp=0xc000067fa0 sp=0xc000067f70 pc=0x439ff3
runtime.bgscavenge(0x0?)
        /home/christian/sdk/go1.19.10/src/runtime/mgcscavenge.go:617 +0x45 fp=0xc000067fc8 sp=0xc000067fa0 pc=0x43a5c5
runtime.gcenable.func2()
        /home/christian/sdk/go1.19.10/src/runtime/mgc.go:179 +0x26 fp=0xc000067fe0 sp=0xc000067fc8 pc=0x430da6
runtime.goexit()
        /home/christian/sdk/go1.19.10/src/runtime/asm_amd64.s:1594 +0x1 fp=0xc000067fe8 sp=0xc000067fe0 pc=0x478581
created by runtime.gcenable
        /home/christian/sdk/go1.19.10/src/runtime/mgc.go:179 +0xaa

goroutine 18 [finalizer wait]:
runtime.gopark(0x5fbc00?, 0xc0001024e0?, 0x0?, 0x0?, 0xc000066770?)
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:363 +0xd6 fp=0xc000066628 sp=0xc000066608 pc=0x44ef36
runtime.goparkunlock(...)
        /home/christian/sdk/go1.19.10/src/runtime/proc.go:369
runtime.runfinq()
        /home/christian/sdk/go1.19.10/src/runtime/mfinal.go:180 +0x10f fp=0xc0000667e0 sp=0xc000066628 pc=0x42ff0f
runtime.goexit()
        /home/christian/sdk/go1.19.10/src/runtime/asm_amd64.s:1594 +0x1 fp=0xc0000667e8 sp=0xc0000667e0 pc=0x478581
created by runtime.createfing
        /home/christian/sdk/go1.19.10/src/runtime/mfinal.go:157 +0x45
exit status 2
```
This issue is explained [here](https://github.com/ggerganov/llama.cpp/issues/317).