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
ms.openlocfilehash: 9761eb5085a77279c4d07d39946a5ad1453ecaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717241"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown-Methode

Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Hinweise  

 Der Profiler-Code kann Methoden der [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstelle nicht sicher aufrufen, nachdem die- `Shutdown` Methode aufgerufen wurde. Alle Aufrufe von `ICorProfilerInfo` Methoden führen zu einem nicht definierten Verhalten, nachdem die- `Shutdown` Methode zurückgegeben wurde. Bestimmte unveränderliche Ereignisse können nach dem Herunterfahren weiterhin auftreten. der Profiler sollte darauf achten, dass Sie sofort zurückkehren, wenn dies auftritt.  
  
 Die- `Shutdown` Methode wird nur aufgerufen, wenn die verwaltete Anwendung, für die die Profilerstellung ausgeführt wird, als verwalteter Code gestartet wird (d. h., der erste Frame im Prozess Stapel wird verwaltet). Wenn die Anwendung als nicht verwalteter Code gestartet, aber später in verwalteten Code gesprungen ist, wird eine Instanz des Common Language Runtime (CLR) erstellt, dann `Shutdown` wird nicht aufgerufen. In diesen Fällen sollte der Profiler in der Bibliothek eine Routine enthalten `DllMain` , die den DLL_PROCESS_DETACH-Wert verwendet, um Ressourcen freizugeben und eine Bereinigungs Verarbeitung der Daten durchzuführen, wie z. b. das Leeren von Ablauf Verfolgungen auf die Festplatte usw.  
  
 Im Allgemeinen muss der Profiler mit unerwarteten Herunterfahr Vorgängen zurechtkommen. Beispielsweise kann ein Prozess durch die Win32's-Methode angehalten werden `TerminateProcess` (in Winbase. h deklariert). In anderen Fällen hält die CLR bestimmte verwaltete Threads (Hintergrundthreads) an, ohne dass dafür ordnungsgemäße Zerstörungs Nachrichten bereitgestellt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [Initialize-Methode](icorprofilercallback-initialize-method.md)
