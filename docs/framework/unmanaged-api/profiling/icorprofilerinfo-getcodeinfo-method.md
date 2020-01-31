---
title: ICorProfilerInfo::GetCodeInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
ms.openlocfilehash: 583189cd667af142ab7d0934be34411644dac936
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863919"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a>ICorProfilerInfo::GetCodeInfo-Methode
Ruft den Wertebereich des nativen Codes ab, der der angegebenen Funktions-ID zugeordnet ist.  
  
 Diese Methode ist veraltet. Verwenden Sie stattdessen die [ICorProfilerInfo2:: GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 [in] Die ID der Funktion, der der systemeigene Code zugeordnet ist.  
  
 `pStart`  
 [out] Ein Zeiger auf ein Array von Bytes, aus denen sich der native Code der Funktion zusammensetzt.  
  
 `pcSize`  
 [out] Ein Zeiger auf eine ganze Zahl, die die Größe des nativen Codes in Bytes angibt.  
  
## <a name="remarks"></a>Hinweise  
 Zur Leistungsoptimierung teilt die Laufzeit in .NET Framework, Version 2.0, den vorkompilierten nativen Code einer Funktion in mehrere Bereiche auf. Daher ist die `GetCodeInfo`-Methode in .NET Framework 2.0 veraltet, weil sie den Wertebereich des systemeigenen Codes einer Funktion nicht verarbeiten kann. Profiler sollten stattdessen die allgemeinere `ICorProfilerInfo2::GetCodeInfo2`-Methode verwenden.  
  
 Diese Funktion verwendet vom Aufrufer reservierte Puffer.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,0  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
