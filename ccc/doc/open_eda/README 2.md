# 開源 IC / EDA 工具

* [開源IC設計工具](openIcEda.md)
* [Verilator](verilator.md): Veriflication
* [YosysHQ](yosishq.md)
* [OpenRoad](openroad.md)
* [pulp](pulp.md)
    * [croc](croc.md)
* [參考文獻](reference.md)

## pulp: 可行的一個 Open Source IC design EDA tool chain


## pulp 使用下列 Open Source Tools

1. Verilator: Verification (Verilog => RTL)
2. YosisHQ: Synthesizer (RTL => Netlist)
3. OpenROAD: Place and Route (Netlist => GDS2)

![](./img/pulpFlow.png)

GDS2: https://en.wikipedia.org/wiki/GDSII

## croc 還使用了下列工具

- [Bender](https://github.com/pulp-platform/bender#installation): Dependency manager
- [Morty](https://github.com/pulp-platform/morty#install): SystemVerilog pickler
- [SVase](https://github.com/pulp-platform/svase#install--build): SystemVerilog pre-elaborator
- [SV2V](https://github.com/zachjs/sv2v#installation): SystemVerilog to Verilog
- [Yosys](https://github.com/YosysHQ/yosys#building-from-source): Synthesis tool
- [OpenRoad](https://github.com/The-OpenROAD-Project/OpenROAD/blob/master/docs/user/Build.md): Place & Route tool
- (Optional) [Verilator](https://github.com/verilator/verilator): Simulator
- (Optional) Questasim/Modelsim: Simulator