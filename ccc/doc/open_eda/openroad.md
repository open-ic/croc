

## ccc: OpenRoad 是什麼？

ChatGPT: https://chatgpt.com/c/673aacbc-e7cc-8012-b8bd-94cefea8373c

OpenRoad 是一個開放原始碼專案，旨在提供免費且高效的電子設計自動化 (Electronic Design Automation, EDA) 工具，用於數位集成電路的設計和實現。該專案的主要目標是推動半導體設計工具的開放性和可訪問性，降低晶片設計的門檻，並支持開源硬體社群。

### 核心功能
1. **數位設計流程整合**：提供從 RTL 到 GDSII（矽晶版佈局）完整的設計流程，包括合成、放置、繞線和優化等階段。
2. **高效演算法**：利用現代化的演算法來提升設計效率，支持工業級應用。
3. **開放協作**：支持與其他開放原始碼專案的整合，例如 SkyWater 開源製程。
4. **可擴展性**：設計工具具有模組化結構，方便開發者擴展功能或改進演算法。

### 使用場景
- **學術研究**：支持大學或研究機構進行半導體設計相關研究。
- **開源晶片設計**：適合創客社群和開源硬體開發者使用。
- **低成本晶片開發**：降低中小型公司或個人設計晶片的成本。

### 關聯專案
OpenRoad 是 **DARPA（美國國防高等研究計劃署）OpenROAD 計畫**的一部分，與其他相關專案（如 OpenLane、SkyWater PDK）共同推動開源硬體生態系統的發展。

你對 OpenRoad 有特定的問題或應用需求嗎？

## ccc: 請給一個 OpenRoad 的例子

以下是一個使用 OpenRoad 工具進行簡單數位電路設計的範例，展示從 RTL 到 GDSII 的流程。這個例子假設我們使用 SkyWater 130nm PDK 和 OpenLane 工具鏈，因為 OpenRoad 通常與 OpenLane 整合使用。

---

### 1. **設計目標**
設計一個簡單的 4 位元加法器，並將其轉換為矽晶版佈局（GDSII）。

---

### 2. **準備設計檔案**
建立一個 Verilog 模組來描述 4 位元加法器：

**檔案名稱**：`adder.v`
```verilog
module adder (
    input [3:0] a,
    input [3:0] b,
    output [4:0] sum
);
    assign sum = a + b;
endmodule
```

---

### 3. **設置 OpenLane 專案**
初始化一個 OpenLane 專案並設置配置檔案：

```bash
mkdir -p ~/openlane/designs/adder
cd ~/openlane/designs/adder
```

建立配置檔案 **`config.json`**：
```json
{
    "DESIGN_NAME": "adder",
    "VERILOG_FILES": "adder.v",
    "CLOCK_PORT": "",
    "CLOCK_PERIOD": 10,
    "SYNTH_STRATEGY": "AREA 0",
    "FP_CORE_UTIL": 50,
    "PL_TARGET_DENSITY": 0.6
}
```

---

### 4. **啟動設計流程**
進入 OpenLane 環境並執行設計流程：

```bash
cd ~/openlane
docker run -it --rm -v $(pwd):/openlane -v /path/to/skywater-pdk:/skywater-pdk openlane:latest
```

執行流程：
```bash
flow.tcl -design ~/openlane/designs/adder
```

---

### 5. **查看中間步驟**
在流程中，OpenRoad 負責以下階段：
- **放置（Placement）**：將標準單元放置於晶片內。
- **繞線（Routing）**：生成連接線路。
- **時序優化（Timing Optimization）**：確保符合設計規範。

使用 OpenRoad CLI 查看放置或繞線結果：

```bash
openroad
read_lef adder.lef
read_def adder.placed.def
gui
```

---

### 6. **生成最終佈局**
最終輸出的檔案將在 `~/openlane/designs/adder/runs/<run-date>/results/gds/adder.gds` 中。

使用檢視工具（例如 Klayout）查看 GDSII 檔案：
```bash
klayout ~/openlane/designs/adder/runs/<run-date>/results/gds/adder.gds
```

---

### 7. **驗證**
進行 DRC（設計規則檢查）和 LVS（佈局與原理圖一致性檢查）：
```bash
magic -T sky130A.tech <adder.gds>
netgen -batch lvs "adder.spice adder" "adder.sch adder"
```

---

這個範例展示了如何使用 OpenRoad 和相關工具完成一個基本的晶片設計。如果你有更詳細的需求或要執行更複雜的設計，我可以提供更進一步的指導！

