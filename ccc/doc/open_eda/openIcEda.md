# ccc: 有哪些開源的 IC 設計工具？

ChatGPT: https://chatgpt.com/c/673a8d83-06f0-8012-9bd9-ebf616f8f433

以下是一些常見的開源 IC 設計工具，涵蓋從硬體描述語言 (HDL) 開發到佈局布線的多個設計階段：

---

### **硬體描述語言 (HDL) 開發**
1. **[Verilator](https://www.veripool.org/verilator/)**
   - 功能：高效能 Verilog/SystemVerilog 模擬器。
   - 特點：將 HDL 轉換為 C++/SystemC 程式碼，適合用於快速模擬和驗證。
   
2. **[Icarus Verilog](https://github.com/steveicarus/iverilog)**
   - 功能：Verilog 編譯器與模擬器。
   - 特點：支持 Verilog-2005，適用於小型設計和教育用途。

3. **[GHDL](https://github.com/ghdl/ghdl)**
   - 功能：VHDL 模擬器。
   - 特點：支持 IEEE 標準的 VHDL，並可以與其他工具（如 GTKWave）配合使用。

---

### **視覺化與波形查看**
1. **[GTKWave](https://gtkwave.sourceforge.net/)**
   - 功能：波形查看工具。
   - 特點：支持多種格式（VCD、LXT、FST 等），可用於模擬結果的分析。

---

### **綜合 (Synthesis) 工具**
1. **[Yosys](https://github.com/YosysHQ/yosys)**
   - 功能：開源綜合工具。
   - 特點：支持 Verilog RTL 綜合，可用於生成比特流或進一步佈局布線。

2. **[SymbiFlow](https://github.com/symbiflow)**
   - 功能：開源 FPGA 設計工具。
   - 特點：支持多種 FPGA 平台（如 Xilinx、Lattice）。

---

### **佈局與布線 (Place and Route)**
1. **[OpenROAD](https://github.com/the-openroad-project)**
   - 功能：從 RTL 到 GDSII 的自動化設計流程。
   - 特點：提供綜合、佈局、布線以及優化的一站式解決方案。

2. **[QFlow](https://github.com/RTimothyEdwards/qflow)**
   - 功能：ASIC 設計流程工具。
   - 特點：整合綜合、佈局、布線以及 DRC/LVS。

---

### **物理設計與驗證**
1. **[Magic](http://opencircuitdesign.com/magic/)**
   - 功能：VLSI 佈局工具。
   - 特點：支持佈局設計、DRC 和 LVS 檢查。

2. **[KLayout](https://www.klayout.de/)**
   - 功能：GDSII 佈局檢視與編輯工具。
   - 特點：支持用於手動佈局和設計檢查。

3. **[Netgen](http://opencircuitdesign.com/netgen/)**
   - 功能：LVS（佈局與網表一致性檢查）。
   - 特點：用於驗證設計的物理與邏輯一致性。

---

### **模擬工具**
1. **[ngspice](http://ngspice.sourceforge.net/)**
   - 功能：模擬 SPICE 電路。
   - 特點：適用於模擬電路行為和特性。

2. **[Xyce](https://xyce.sandia.gov/)**
   - 功能：高效能 SPICE 模擬器。
   - 特點：支持大型電路的模擬，尤其適合並行計算。

---

### **完整設計平台**
1. **[OpenLANE](https://github.com/The-OpenROAD-Project/OpenLane)**
   - 功能：基於開源工具的完整 ASIC 設計流程。
   - 特點：集成 RTL、綜合、佈局布線、DRC 和 LVS 等工具。

2. **[Chipyard](https://chipyard.readthedocs.io/en/latest/)**
   - 功能：RISC-V SOC 開發平台。
   - 特點：結合多種開源工具進行 RISC-V 處理器的設計和模擬。

---

這些工具的組合可以支持從 FPGA 設計到 ASIC 製造的完整工作流程，並且社群活躍，適合開源與學術研究使用。