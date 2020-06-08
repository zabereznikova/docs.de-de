---
title: ICorProfilerInfo::EndInprocDebugging-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
ms.openlocfilehash: afbb007b6293e6e9cff92281a6f5e93b1e7924ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502976"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a>ICorProfilerInfo::EndInprocDebugging-Methode
Beendet eine in-Process-Debuggingsitzung. Diese Methode ist in der .NET Framework Version 2,0 veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwProfilerContext`  
 in Ein-Wert, der die Debugsitzung angibt. Dieser Wert muss mit dem übereinstimmen, der in der [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) -Methode empfangen wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie müssen [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) und `EndInprocDebugging` innerhalb derselben Rückruf Methode aufrufen.  
  
 Die CLR-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in den .NET Framework-Versionen 1,0 und 1,1. Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden. Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die mit der Profilerstellungs-API mehr übereinstimmen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Version:** 1,0  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
