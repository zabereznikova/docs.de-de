---
title: ICorProfilerCallback::Shutdown-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1696cb49170ba245a657e5efb6c8ba4b694af32f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041755"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown-Methode
Benachrichtigt den Profiler an, dass die Anwendung heruntergefahren wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Profilercode kann nicht sicher Methoden zum Aufrufen der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstelle nach der `Shutdown` Methode wird aufgerufen. Alle Aufrufe von `ICorProfilerInfo` Methoden zu nicht definiertem Verhalten nach der `Shutdown` Methodenrückgabe. Bestimmte unveränderliche Ereignisse können weiterhin nach dem Herunterfahren auftreten. der Profiler sollte sorgfältig und zurückgeben, sofort, wenn dies der Fall.  
  
 Die `Shutdown` Methode wird nur aufgerufen, wenn die verwaltete Anwendung, die ein Profil erstellt wird als verwalteter Code gestartet wurde (d. h. der erste Frame im Stapel Prozess verwaltet wird). Wenn die Anwendung gestartet wird, als nicht verwalteter Code, aber später erfolgte ein in verwaltetem Code Sprung, wodurch eine Instanz von die common Language Runtime (CLR), klicken Sie dann `Shutdown` wird nicht aufgerufen werden. In diesen Fällen sollte der Profiler in der Bibliothek enthalten eine `DllMain` Routine, die das DLL_PROZESS_DETACH verwendet Wert, um alle Ressourcen freizugeben und verarbeiten Sie die Bereinigung seiner Daten, z.B. das Leeren der ablaufverfolgungen auf dem Datenträger und so weiter.  
  
 Im Allgemeinen muss der Profiler mit unerwartetem Herunterfahren umgehen können. Beispielsweise kann ein Prozess angehalten werden, von einer Win32 `TerminateProcess` Methode (deklariert in Winbase.h). In anderen Fällen wird die CLR bestimmte verwaltete Threads (Hintergrundthreads) angehalten, ohne die ordnungsgemäße Zerstörung Nachrichten für diese Bereitstellung verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Initialize-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
