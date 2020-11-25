---
title: ICorProfilerInfo4::InitializeCurrentThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: 51f16523c00cc3dd95b786f1586ccfd75ce8d5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733827"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread-Methode

Initialisiert den aktuellen Thread vor nachfolgenden Profiler-API-aufrufen im gleichen Thread, sodass der Deadlock vermieden werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Hinweise  

 `InitializeCurrentThread`Es wird empfohlen, für jeden Thread aufzurufen, der eine Profiler-API aufruft, während Angehaltene Threads vorhanden sind. Diese Methode wird in der Regel von samplingprofilergeräten verwendet, die ihren eigenen Thread erstellen, um die [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode aufzurufen, während der Zielthread angehalten wird. Durch einen Aufruf von `InitializeCurrentThread` einmal, wenn der Profiler erstmalig den Samplingthread erstellt, können Profiler sicherstellen, dass die verzögerte Initialisierung pro Thread, die die CLR andernfalls während des ersten Aufrufs von ausführen würde, `DoStackSnapshot` nun sicher auftreten kann, wenn keine anderen Threads angehalten werden  
  
> [!NOTE]
> `InitializeCurrentThread` führt die Initialisierung im Voraus aus, um Aufgaben abzuschließen, die Sperren akzeptieren und möglicherweise einen Deadlock verursachen. Wird nur aufgerufen, wenn keine angehaltenen `InitializeCurrentThread` Threads vorhanden sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
