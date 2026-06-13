# DataScience_MachineLearning----End-To-End_ModelBuilding----Cyber-Security-Case-Study_project
# Cyber Security Intrusion Detection: Binary & Multiclass Classification Case Study

This repository contains a comprehensive data science case study focused on Network Intrusion Detection. Using network traffic telemetry and connection session flags, the objective is to build machine learning models capable of:
1. **Binary Classification:** Accurately distinguishing between standard network traffic (`Normal`) and anomalous or malicious traffic (`Attack`).
2. **Multiclass Classification:** Categorizing specific variants of cyber-attack vectors across distinct threat families (DoS, Probing, U2R, R2L).

---

## 📂 Dataset Repository & Structure

The dataset comprises **11 CSV files**, each tracking a specific type of connection signature. Every file contains **41 numeric/categorical features** mapping network connection attributes.

### Complete Dataset Summary

| File Name | Attack / Traffic Type | Attack Category | Records Count | File Size | Structural Quirks / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `Data_of_Attack_Back_Normal.csv` | Normal Operations | Benign Traffic | 576,710 | 69.15 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_Neptune.csv` | Neptune Attack | DoS (Denial of Service) | 227,228 | 27.83 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_Satan.csv` | Satan Attack | Probing / Scanning | 5,019 | 0.62 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_Smurf.csv` | Smurf Attack | DoS (Denial of Service) | 3,007 | 0.35 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_PortSweep.csv`| PortSweep Attack | Probing / Scanning | 2,964 | 0.37 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_NMap.csv` | NMap Scan | Probing / Scanning | 1,554 | 0.18 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back.csv` | Back Attack | DoS (Denial of Service) | 968 | 0.12 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_GuessPassword.csv`| Guess Password | R2L (Remote to Local) | 53 | 0.01 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_BufferOverflow.csv`| Buffer Overflow | U2R (User to Root) | 30 | < 0.01 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_RootKit.csv` | Rootkit Deployment| U2R (User to Root) | 10 | < 0.01 MB | Contains standard headers with leading spaces |
| `Data_of_Attack_Back_FTPWrite.csv` | Anonymous FTP Write| R2L (Remote to Local) | 7 | < 0.01 MB | **Missing Header Row.** Data starts on line 1. |

---

## ⚠️ Data Ingestion & Formatting Quirks

When loading this data into pandas/Python pipelines, resolve the following structural details:

1. **Leading Whitespaces in Headers:** Except for `duration`, almost every feature name contains a leading blank space (e.g., `" protocol_type"`, `" service"`). Fix this immediately post-load:
   ```python
   df.columns = df.columns.str.strip()
IMPORTANT : THE FOLDER IS IN ZIP FILE TO VIEW IT COMPLITELY DOWNLOAD IT FIRST
