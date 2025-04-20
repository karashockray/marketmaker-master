# marketmaker-master
On-chain market maker tools

##### 项目结构

```markdown

├── client        # 跨服务引用 
├── cmd           # 启动服务 
│   ├── config    # 环境配置
│   ├── logs      # 日志
│   └── main.go   # 入口文件
├── internal      # 核心源码分模块 
│   ├── handler   # 控制层
│   ├── logic     # 逻辑层
│   └── model     # 数据层
├── router        # 路由层
├── pkg           # 通用工具库 
├── vendor        # 依赖库
├── go.mod        # Go MOD 包管理
├── go.sum
└── README.md     # 说明文档

```

##### 启动命令

```
go run main.go

```

##### 打包命令

```
go build

```

##### windows系统打包linux包

```
set CGO_ENABLED=1 GOARCH=amd64  CC=x86_64-windows-musl-gcc  CXX=x86_64-windows-musl-g++ 
set GOOS=linux
set CGO_ENABLED=1 GOARCH=amd64  CC=x86_64-linux-musl-gcc  CXX=x86_64-linux-musl-g++ 

go build

```
生成ABI go文件
abigen --abi V2Router.abi --bin V2Router.bin --pkg V2Router --out V2Router.go

abigen --abi V2ERC20Token.abi --bin V2ERC20Token.bin --pkg V2ERC20Token --out V2ERC20Token.go

abigen --abi V2Pair.abi --bin V2Pair.bin --pkg V2Pair --out V2Pair.go

abigen --abi IUniswapV2Pair.abi --bin IUniswapV2Pair.bin --pkg IUniswapV2Pair --out IUniswapV2Pair.go
abigen --abi IUniswapV2Pair.abi --pkg IUniswapV2Pair --out IUniswapV2Pair.go
abigen --abi UniswapV2Router02.abi --pkg UniswapV2Router02 --out UniswapV2Router02.go
