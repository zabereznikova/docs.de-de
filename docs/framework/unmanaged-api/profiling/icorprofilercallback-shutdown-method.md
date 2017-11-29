---
title: ICorProfilerCallback::Shutdown-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea738414c21536377705260646e0f0684442492d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown-Methode
Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Profilercode kann nicht sicher Aufrufen von Methoden der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstelle nach der `Shutdown` -Methode aufgerufen wird. Alle Aufrufe von `ICorProfilerInfo` Methoden zu nicht definiertem Verhalten nach der `Shutdown` -Methode zurückkehrt. Bestimmte unveränderliche Ereignisse können nach dem Herunterfahren weiterhin auftreten. der Profiler sollte zurückgeben, sofort, wenn in diesem Fall kümmern.  
  
 Die `Shutdown` Methode wird nur aufgerufen, wenn die verwaltete Anwendung, die ein Profil erstellt wird als verwalteter Code gestartet (d. h. der erste Frame auf dem Stapel Prozess verwaltet wird). Wenn die Anwendung als nicht verwalteter Code gestartet, jedoch später erfolgte ein in verwaltetem Code Sprung, wodurch eine Instanz von der common Language Runtime (CLR), klicken Sie dann `Shutdown` wird nicht aufgerufen werden. In diesen Fällen sollte der Profiler in der Bibliothek enthalten eine `DllMain` Routine, die die DLL_PROCESS_DETACH verwendet der Wert, der alle Ressourcen frei und führt eine Bereinigung Verarbeitung seiner Daten wie z. B. das leeren von ablaufverfolgungen und so weiter auf den Datenträger.  
  
 Im Allgemeinen muss der Profiler mit unerwartetem Herunterfahren bewältigen. Beispielsweise kann ein Prozess von einer Win32 angehalten `TerminateProcess` (deklariert in Winbase.h) Methode. In anderen Fällen wird die CLR bestimmte verwaltete Threads (Hintergrundthreads) angehalten, ohne ordnungsgemäßes Zerstörung Nachrichten für diese Bereitstellung verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Initialize-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
