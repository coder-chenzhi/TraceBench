## Goal
Load TraceBench data into database to boost the analysis process

## TraceBench Introduction
Open sourced by
Execution traces of HDFS under various environment, traces are collected by MTracer
361 files, 366,478 traces, 14,724,959 events, 6,273,497 edges
Different files are collected under different situation, and the filename explain the situation implicitly

### Sample filename
> AN_Data_corruptBlk_r_00FDN_30C_1to19B_0to120INT_15RT_5WT.sql
AN_Data_corruptMeta_r_20FDN_30C_1to19B_0to120INT_15RT_5WT.sql
AN_Net_disconnectDN_r_05FDN_30C_1to19B_0to120INT_15RT_5WT.sql
COM_Mul_AA_rwrpc_1_30C_1to19B_0to120INTR_0to600INTW_0to0INTRPC_150RT_10WT.sql
COM_Sin_Proc_rwrpc_2_30C_1to19B_0to120INTR_0to600INTW_0to0INTRPC_60RT_10WT.sql
NM_CL_r_20C_1to19B_0to120INT_50RT_10WT.sql
NM_CL_rpc_30C_0to0INT_10RT_1WT.sql
NM_CL_rw_35C_1to19B_0to120INTR_0to600INTW_50RT_10WT.sql
NM_DN_rw_10DN_30C_1to19B_0to120INTR_0to600INTW_50RT_10WT.sql
NM_DN_w_05DN_30C_1to19B_0to600INT_50RT_10WT.sql


## Design

### Class

**DatabaseFactory**
instantiation DatabaseConnector from user-specific configurations

**DatabaseConnector**

**Context**
???
define a new class to contain all possible context?

**TraceFile**
attributes = [filename, state, failureType, failureOperation, workloadType, workload, ...]

**Edge**
attributes = [TaskID, FatherTID, FatherStartTime, ChildTID]

**Operation**
attributes = [OpName, Num, MaxDelay, MinDelay, AverageDelay]
key = [OpName]

**Report**
attributes = [TaskID, TID, OpName, StartTime, EndTime, HostAddress, HostName, Agent, Description]

**Task**
attributes = [TaskID, Title, NumReports, NumEdges, FirstSeen, LastUpdated, StartTime, EndTime]

**Analysis**
get all
method = []


