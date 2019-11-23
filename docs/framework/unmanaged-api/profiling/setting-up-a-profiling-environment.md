---
title: Einrichten einer Profilerstellungsumgebung
ms.date: 03/30/2017
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
ms.openlocfilehash: 86720cb1739e3f193cd1d5081577d69bca1cf0f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427051"
---
# <a name="setting-up-a-profiling-environment"></a>Einrichten einer Profilerstellungsumgebung
> [!NOTE]
> There have been substantial changes to profiling in the .NET Framework 4.  
  
 Wenn ein verwalteter Prozess (Anwendung oder Dienst) gestartet wird, wird die Common Language Runtime (CLR) geladen. Wenn die CLR initialisiert wird, werden die folgenden zwei Umgebungsvariablen ausgewertet, um zu entscheiden, ob der Prozess mit einem Profiler verbunden werden soll:  
  
- COR_ENABLE_PROFILING: Die CLR stellt nur dann eine Verbindung zu einem Profiler her, wenn diese Umgebungsvariable vorhanden und auf 1 gesetzt ist.  
  
- COR_PROFILER: Wenn die Prüfung auf die Variable COR_ENABLE_PROFILING erfolgreich abgeschlossen wurde, stellt die CLR eine Verbindung mit dem Profiler mit dieser CLSID oder ProgID her, die zuvor in der Registrierung abgelegt worden sein muss. Die COR_PROFILER-Umgebungsvariable ist als Zeichenfolge definiert, wie in den beiden folgenden Beispielen gezeigt.  
  
    ```cpp  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 Zur Profilerstellung für eine CLR-Anwendung müssen die Umgebungsvariablen COR_ENABLE_PROFILING und COR_PROFILER festgelegt werden, bevor Sie die Anwendung ausführen. Außerdem müssen Sie sicherstellen, dass die Profiler-DLL registriert ist.  
  
> [!NOTE]
> Starting with the .NET Framework 4, profilers do not have to be registered.  
  
> [!NOTE]
> To use .NET Framework versions 2.0, 3.0, and 3.5 profilers in the .NET Framework 4 and later versions, you must set the COMPLUS_ProfAPI_ProfilerCompatibilitySetting environment variable.  
  
## <a name="environment-variable-scope"></a>Umgebungsvariablenbereich  
 Die Werte, die Sie für die Umgebungsvariablen COR_ENABLE_PROFILING und COR_PROFILER festlegen, bestimmen den Einflussbereich dieser Variablen. Sie haben folgende Möglichkeiten, diese Variablen festzulegen:  
  
- If you set the variables in an [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) call, they will apply only to the application that you are running at the time. (Sie gelten auch für andere Anwendungen, die von dieser Anwendung gestartet werden und die die Umgebung erben.)  
  
- Wenn Sie die Variablen in einer Eingabeaufforderung festlegen, gelten sie für alle Anwendungen, die von diesem Fenster aus gestartet werden.  
  
- Wenn Sie die Variablen auf Benutzerebene festlegen, gelten sie für alle Anwendungen, die Sie mit Datei-Explorer starten. Eine Eingabeaufforderung, die Sie nach dem Festlegen dieser Variablen öffnen, hat diese Umgebungseinstellungen, ebenso wie jede Anwendung, die Sie aus diesem Fenster starten. To set environment variables at the user level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, and add the variables to the **User variables** list.  
  
- Wenn Sie die Variablen auf Computerebene festlegen, gelten sie für alle Anwendungen, die auf diesem Computer gestartet werden. Eine Eingabeaufforderung, die Sie auf diesem Computer öffnen, hat diese Umgebungseinstellungen, ebenso wie jede Anwendung, die Sie aus diesem Fenster starten. Dies bedeutet, dass jeder verwaltete Prozess auf diesem Computer mit Ihrem Profiler startet. To set environment variables at the computer level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, add the variables to the **System variables** list, and then restart your computer. Nach dem Neustart sind die Variablen systemweit verfügbar.  
  
 Wenn Sie ein Profil für einen Windows-Dienst erstellen, müssen Sie nach dem Festlegen der Umgebungsvariablen und dem Registrieren der Profiler-DLL den Computer neu starten. For more information about these considerations, see the section [Profiling a Windows Service](#windows_service).  
  
## <a name="additional-considerations"></a>Weitere Überlegungen  
  
- The profiler class implements the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces. In .NET Framework, Version 2.0, muss ein Profiler `ICorProfilerCallback2` implementieren. Wenn dies nicht geschieht, wird `ICorProfilerCallback2` nicht geladen.  
  
- Nur ein einzelner Profiler kann ein Profil für einen Prozess zu einem gegebenen Zeitpunkt in einer gegebenen Umgebung erstellen. Sie können zwei verschiedene Profiler in anderen Umgebungen registrieren, doch in jedem müssen Profile für gesonderte Prozesse erstellt werden. Der Profiler muss als prozessinterne COM-Server-DLL implementiert werden, die im gleichen Adressbereich wie der Prozess zugeordnet wird, für den ein Profil erstellt wird. Dies bedeutet, dass der Profiler prozessintern ausgeführt wird. .NET Framework unterstützt keinen anderen Typ von COM-Server. Wenn beispielsweise ein Profiler Anwendungen von einem Remotecomputer aus überwachen möchte, muss er Collector-Agents auf jedem Computer implementieren. Diese Agents fassen die Ergebnisse in Stapeln zusammen und melden diese dem zentralen Datenerfassungscomputer.  
  
- Da der Profiler ein COM-Objekt ist, das prozessintern instanziiert wird, verfügt jede Anwendung mit Profil über eine eigene Kopie des Profilers. Daher muss eine einzelne Profilerinstanz nicht Daten von mehreren Anwendungen behandeln. Sie müssen jedoch eine Logik zum Protokollierungscode des Profilers hinzufügen, um zu verhindern, dass die Protokolldatei durch andere Anwendungen mit Profil überschrieben wird.  
  
## <a name="initializing-the-profiler"></a>Initialisieren des Profilers  
 Wenn die Prüfung auf beide Umgebungsvariablen erfolgreich ist, erstellt die CLR eine Instanz des Profilers in ähnlicher Weise wie für die COM-`CoCreateInstance`-Funktion. Der Profiler wird nicht durch einen direkten Aufruf von `CoCreateInstance` geladen. Deshalb wird ein Aufruf von `CoInitialize`, der das Festlegen des Threadingmodells erfordert, vermieden. The CLR then calls the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method in the profiler. Die Signatur dieser Methode wird im Folgenden beschrieben.  
  
```cpp  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 The profiler must query `pICorProfilerInfoUnk` for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interface pointer and save it so that it can request more information later during profiling.  
  
## <a name="setting-event-notifications"></a>Festlegen von Ereignisbenachrichtigungen  
 The profiler then calls the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to specify which categories of notifications it is interested in. Wenn für den Profiler z. B. nur Benachrichtigungen zum Starten und Verlassen von Funktionen und an Garbage Collection-Benachrichtigungen von Belang sind, wird Folgendes angegeben.  
  
```cpp  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 Durch das Festlegen der Benachrichtigungsmaske in dieser Weise kann der Profiler die Benachrichtigungen einschränken, die er empfängt. Dieser Ansatz hilft dem Benutzer dabei, einen einfachen oder zweckgebundenen Profiler zu erstellen. Er reduziert auch die CPU-Zeit, die durch das Senden von Benachrichtigungen verschwendet würde, die vom Profiler einfach ignoriert werden.  
  
 Bestimmte Profilerereignisse sind unveränderlich. Das bedeutet, dass diese Ereignisse unmittelbar nach ihrem Festlegen im `ICorProfilerCallback::Initialize`-Rückruf nicht deaktiviert und neue Ereignisse nicht aktiviert werden können. Versuche, ein unveränderliches Ereignis zu ändern, führen dazu, dass `ICorProfilerInfo::SetEventMask` ein fehlgeschlagenes HRESULT zurückgibt.  
  
<a name="windows_service"></a>   
## <a name="profiling-a-windows-service"></a>Profilerstellung für einen Windows-Dienst  
 Die Profilerstellung für einen Windows-Dienst ist mit der Profilerstellung für eine Common Language Runtime-Anwendung vergleichbar. Beide Profilerstellungsvorgänge werden durch Umgebungsvariablen aktiviert. Da ein Windows-Dienst gestartet wird, wenn das Betriebssystem gestartet wird, müssen die zuvor in diesem Thema erläuterten Umgebungsvariablen bereits vor dem Systemstart vorhanden und auf die erforderlichen Werte festgelegt sein. Außerdem muss die Profilerstellungs-DLL bereits auf dem System registriert sein.  
  
 Nachdem Sie die COR_ENABLE_PROFILING-Umgebungsvariable und die COR_PROFILER-Umgebungsvariable festgelegt und die Profiler-DLL registriert haben, sollten Sie den Zielcomputer neu starten, damit der Windows-Dienst diese Änderungen feststellen kann.  
  
 Beachten Sie, dass diese Änderungen die Profilerstellung auf einer systemweiten Basis aktivieren. Um zu verhindern, dass für jede nachfolgend ausgeführte verwaltete Anwendung ein Profil erstellt wird, sollten Sie die Systemumgebungsvariablen nach dem Neustart des Zielcomputers löschen.  
  
 Dieses Verfahren führt außerdem dazu, dass für jeden CLR-Prozess ein Profil erstellt wird. The profiler should add logic to its [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback to detect whether the current process is of interest. Wenn dies nicht der Fall ist, kann der Profiler den Rückruf mit einem Fehler abschließen, ohne die Initialisierung auszuführen.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)
