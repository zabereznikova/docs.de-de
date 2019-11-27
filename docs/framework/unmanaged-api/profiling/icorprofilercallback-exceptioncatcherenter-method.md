---
title: ICorProfilerCallback::ExceptionCatcherEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9c9cd0b042dc22f35c38e349ab8881dafc602731
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445015"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter-Methode
Benachrichtigt den Profiler, dass das Steuerelement an den entsprechenden `catch`-Block übermittelt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 in Der Bezeichner der Funktion, die den `catch` Block enthält.  
  
 `objectId`  
 in Der Bezeichner der Ausnahme, die behandelt wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `ExceptionCatcherEnter`-Methode wird nur aufgerufen, wenn sich der Catch-Punkt im Code befindet, der mit dem JIT-Compiler (Just-in-Time) kompiliert wurde. Eine Ausnahme, die in nicht verwaltetem Code oder im internen Code der Laufzeit abgefangen wird, ruft diese Benachrichtigung nicht auf. Der `objectId` Wert wird erneut weitergegeben, da ein Garbage Collection das Objekt seit der `ExceptionThrown` Benachrichtigung verschieben könnte.  
  
 Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden. Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.  
  
 Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ExceptionCatcherLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
