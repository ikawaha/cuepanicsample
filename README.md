```
$ go version
go version go1.22.0 darwin/arm64
```
```
$ cue version
cue version v0.7.0

go version go1.21.5
      -buildmode exe
       -compiler gc
       -trimpath true
  DefaultGODEBUG panicnil=1
     CGO_ENABLED 1
          GOARCH arm64
            GOOS darwin
```


```
$ go get github.com/ikawaha/cuepanicsample && cue get go github.com/ikawaha/cuepanicsample
go: github.com/ikawaha/cuepanicsample@v0.0.0-20240209121021-6e4bb697dd47 requires go >= 1.22.0; switching to go1.22.0
go: upgraded go 1.21.5 => 1.22.0
go: added github.com/ikawaha/cuepanicsample v0.0.0-20240209121021-6e4bb697dd47
panic: runtime error: invalid memory address or nil pointer dereference [recovered]
	panic: runtime error: invalid memory address or nil pointer dereference
[signal SIGSEGV: segmentation violation code=0x2 addr=0x18 pc=0x104ae1778]

goroutine 1 [running]:
cuelang.org/go/cmd/cue/cmd.recoverError(0x1400055de60)
	cuelang.org/go/cmd/cue/cmd/root.go:323 +0x94
panic({0x104d12420?, 0x1053127e0?})
	runtime/panic.go:914 +0x218
cuelang.org/go/cmd/cue/cmd.(*extractor).recordConsts(0x1400053e360, 0x140003b2300?)
	cuelang.org/go/cmd/cue/cmd/get_go.go:621 +0x108
cuelang.org/go/cmd/cue/cmd.(*extractor).extractPkg(0x1400053e360, {0x14000036064, 0x17}, 0x140003b2300)
	cuelang.org/go/cmd/cue/cmd/get_go.go:447 +0xc94
cuelang.org/go/cmd/cue/cmd.extract(0x140004f9680, {0x1400052c2a0, 0x1, 0x1})
	cuelang.org/go/cmd/cue/cmd/get_go.go:416 +0x2f8
cuelang.org/go/cmd/cue/cmd.newGoCmd.mkRunE.func1(0x14000505f00?, {0x1400052c2a0, 0x1, 0x1})
	cuelang.org/go/cmd/cue/cmd/root.go:92 +0x90
github.com/spf13/cobra.(*Command).execute(0x14000517500, {0x1400052c260, 0x1, 0x1})
	github.com/spf13/cobra@v1.7.0/command.go:940 +0x66c
github.com/spf13/cobra.(*Command).ExecuteC(0x1400044f800)
	github.com/spf13/cobra@v1.7.0/command.go:1068 +0x320
github.com/spf13/cobra.(*Command).Execute(...)
	github.com/spf13/cobra@v1.7.0/command.go:992
cuelang.org/go/cmd/cue/cmd.(*Command).Run(0x140004f9680, {0x3?, 0x3?})
	cuelang.org/go/cmd/cue/cmd/root.go:308 +0x5c
cuelang.org/go/cmd/cue/cmd.Main()
	cuelang.org/go/cmd/cue/cmd/root.go:236 +0x74
main.main()
	cuelang.org/go/cmd/cue/main.go:24 +0x1c
```
