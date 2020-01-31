---
title: ICorProfilerInfo::BeginInprocDebugging-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: c14979fa711145b9f1a134f90d7450b24e6d8a15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864296"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a>ICorProfilerInfo::BeginInprocDebugging-Methode
Initialisiert die Prozess interne Debugunterstützung. Diese Methode ist in der .NET Framework Version 2,0 veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a>Parameters  
 `fThisThreadOnly`  
 in Legen Sie diesen Wert auf `true` fest, um die Debugunterstützung nur für den aktuellen Thread zu initialisieren. Legen Sie Sie auf `false`, um die Debugunterstützung für alle Threads zu initialisieren.  
  
 `pdwProfilerContext`  
 vorgenommen Der Zeiger auf einen zurückgegebenen Wert, der die Debugsitzung identifiziert.  
  
## <a name="remarks"></a>Hinweise  
 Die CLR-debuggingdienste unterstützten das eingeschränkte Prozess interne Debuggen in den .NET Framework-Versionen 1,0 und 1,1. Das Prozess interne Debuggen ermöglichte es einem Profiler, die Inspektions Teile der Debug-API zu verwenden. Aufgrund des Feedbacks von Kunden wurde das Prozess interne Debuggen aus der .NET Framework in Version 2,0 entfernt und durch eine Reihe von Funktionen ersetzt, die mit der Profilerstellungs-API mehr übereinstimmen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Version:** 1,0  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
