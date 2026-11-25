# 山西省 2014—2025 年逐日 NOₓ 排放反演数据集

本数据集配套论文《基于多源卫星数据衔接的山西省长时序NOx排放反演与时空演变分析》，包含山西省 2014—2025 年的逐日 NOₓ 排放通量和反演标准差。

## 数据下载

[查看 v1.0.0 发布页](https://github.com/xumeyao/shanxi-nox-daily-emissions-2014-2025/releases/tag/v1.0.0)。按年份下载所需分包：

- [2014—2015 年](https://github.com/xumeyao/shanxi-nox-daily-emissions-2014-2025/releases/download/v1.0.0/Shanxi_NOx_Daily_Emissions_2014_2015.zip)
- [2016—2017 年](https://github.com/xumeyao/shanxi-nox-daily-emissions-2014-2025/releases/download/v1.0.0/Shanxi_NOx_Daily_Emissions_2016_2017.zip)
- [2018—2021 年](https://github.com/xumeyao/shanxi-nox-daily-emissions-2014-2025/releases/download/v1.0.0/Shanxi_NOx_Daily_Emissions_2018_2021.zip)
- [2022—2025 年](https://github.com/xumeyao/shanxi-nox-daily-emissions-2014-2025/releases/download/v1.0.0/Shanxi_NOx_Daily_Emissions_2022_2025.zip)

四个分包含 12 个年度 MAT 文件，每个分包均附中文 `README.txt`。文件名格式为 `Shanxi_NOx_Daily_Emissions_YYYY.mat`，其中 `YYYY` 为年份。

## 变量与单位

| 变量 | 含义 | 单位 |
|---|---|---|
| `nox_emission_flux` | 逐日 NOₓ 排放通量 | μg·m⁻²·d⁻¹ |
| `nox_emission_flux_std` | 逐日排放反演标准差 | μg·m⁻²·d⁻¹ |
| `longitude` | 网格中心经度 | °E |
| `latitude` | 网格中心纬度 | °N |
| `units` | 记录变量单位的 MATLAB 结构体 | — |

两个通量数组在 MATLAB 中按 `[经度, 纬度, 日期]` 排列，尺寸为 `112 × 142 × 365`，闰年为 `112 × 142 × 366`。第 1 层对应当年 1 月 1 日，`NaN` 表示缺测或无可用结果。两种通量变量除以 86,400 可换算为论文图表所用的 μg·m⁻²·s⁻¹。

结果统一存储在 0.05° 网格上。2014 年 1 月至 2018 年 4 月的卫星输入为 0.25° 的 HSTCM-NO₂ 数据，2018 年 5 月起使用 TROPOMI 数据。
