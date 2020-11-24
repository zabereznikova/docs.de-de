---
title: ICorProfilerInfo::GetInprocInspectionIThisThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: 8daa84e3abbbc64c9a48d8957b4ad9c6756d0d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682080"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a>ICorProfilerInfo::GetInprocInspectionIThisThread-Methode

Ruft ein Objekt ab, das für die ICorDebugThread-Schnittstelle abgefragt werden kann. Diese Methode ist in der .NET Framework Version 2,0 veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppicd`  
 [out](/cpp/atl/iunknown) -Objekt, das für die-Schnittstelle abgefragt werden kann `ICorDebugThread` .  
  
## <a name="remarks"></a>Hinweise  

 Die Common Language Runtime (CLR)-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in Version 1,0 von .NET Framework. Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden. Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die sich besser mit der Profilerstellungs-API in Einklang setzen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Version:** 1,0  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
