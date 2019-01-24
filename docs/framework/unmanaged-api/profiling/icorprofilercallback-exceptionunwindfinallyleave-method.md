---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7641569bc97ab241cfba355e91e73567843ea328
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637780"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a>ICorProfilerCallback::ExceptionUnwindFinallyLeave-Methode
Benachrichtigt den Profiler, die der Entladephase der Behandlung verlassen hat eine `finally` Klausel.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler sollte während dieses Aufrufs nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann. Wenn hier die Profiler-Blöcke und eine Garbagecollection wird versucht, blockiert die Laufzeit, bis dieser Rückruf zurückgegeben.  
  
 Darüber hinaus muss bei Aufruf wird der Profiler Aufrufen nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ExceptionUnwindFinallyEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
