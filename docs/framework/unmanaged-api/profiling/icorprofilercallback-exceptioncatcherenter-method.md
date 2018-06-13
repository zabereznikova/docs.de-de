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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8a87fb05a49c2813cf4d299c3663419be1640b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450829"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter-Methode
Benachrichtigt den Profiler, der in das entsprechende Steuerelement übergeben wird `catch` Block.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Der Bezeichner von die Funktion mit dem `catch` Block.  
  
 `objectId`  
 [in] Der Bezeichner für die Ausnahme verarbeitet wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `ExceptionCatcherEnter` Methode wird nur aufgerufen, wenn der Catch-Punkt im Code mit der Just-in-Time (JIT)-Compiler kompiliert wird. Eine Ausnahme, die in nicht verwaltetem Code oder im internen Code der Laufzeit abgefangen wird wird diese Benachrichtigung nicht aufgerufen werden. Die `objectId` erneut Wert übergeben wird, da eine Garbagecollection verschoben haben, das Objekt seit konnte die `ExceptionThrown` Benachrichtigung.  
  
 Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann. Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.  
  
 Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ExceptionCatcherLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
