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
ms.openlocfilehash: 63e41df8af85d94df068526ef69708687b341e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446946"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown-Methode
Benachrichtigt den Profiler, dass die Anwendung heruntergefahren wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler-Code kann Methoden der [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) -Schnittstelle nicht sicher aufrufen, nachdem die `Shutdown`-Methode aufgerufen wurde. Alle Aufrufe von `ICorProfilerInfo` Methoden führen zu einem nicht definierten Verhalten, nachdem die `Shutdown`-Methode zurückgegeben wurde. Bestimmte unveränderliche Ereignisse können nach dem Herunterfahren weiterhin auftreten. der Profiler sollte darauf achten, dass Sie sofort zurückkehren, wenn dies auftritt.  
  
 Die `Shutdown`-Methode wird nur aufgerufen, wenn die verwaltete Anwendung, für die die Profilerstellung ausgeführt wird, als verwalteter Code gestartet wird (d. h., der erste Frame im Prozess Stapel wird verwaltet). Wenn die Anwendung als nicht verwalteter Code gestartet, aber später in verwalteten Code gesprungen ist, wodurch eine Instanz des Common Language Runtime (CLR) erstellt wird, wird `Shutdown` nicht aufgerufen. In diesen Fällen sollte der Profiler in der Bibliothek eine `DllMain` Routine enthalten, die den DLL_PROCESS_DETACH-Wert verwendet, um Ressourcen freizugeben und die Bereinigung Ihrer Daten durchzuführen, wie z. b. das Leeren von Ablauf Verfolgungen auf die Festplatte usw.  
  
 Im Allgemeinen muss der Profiler mit unerwarteten Herunterfahr Vorgängen zurechtkommen. Beispielsweise kann ein Prozess durch Win32's `TerminateProcess`-Methode (deklariert in Winbase. h) angehalten werden. In anderen Fällen hält die CLR bestimmte verwaltete Threads (Hintergrundthreads) an, ohne dass dafür ordnungsgemäße Zerstörungs Nachrichten bereitgestellt werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Initialize-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
