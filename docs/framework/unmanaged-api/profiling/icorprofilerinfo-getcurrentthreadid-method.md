---
title: ICorProfilerInfo::GetCurrentThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863945"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a>ICorProfilerInfo::GetCurrentThreadID-Methode
Ruft die ID des aktuellen Threads ab, wenn es sich um einen verwalteten Thread handelt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a>Parameters  
 `pThreadId`  
 vorgenommen Ein Zeiger auf die zurückgegebene ID des verwalteten Threads.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der aktuelle Thread ein interner Lauf Zeit Thread oder ein anderer nicht verwalteter Thread ist, gibt `GetCurrentThreadID` CORPROF_E_NOT_MANAGED_THREAD als HRESULT zurück, und der zurückgegebene Wert des `pThreadId`-Parameters ist NULL.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
