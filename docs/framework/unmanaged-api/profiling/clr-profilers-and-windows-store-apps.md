---
title: CLR-Profiler und Windows Store-Apps
ms.date: 03/30/2017
dev_langs:
- csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1747d99fbfbc31fb592aee570d10d574b8480b0
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743812"
---
# <a name="clr-profilers-and-windows-store-apps"></a>CLR-Profiler und Windows Store-Apps

In diesem Thema wird erläutert, was Sie denken Sie beim Schreiben von Diagnosetools, die Analysieren von verwaltetem Code, die in einer Windows Store-app ausgeführt wird.  Darüber hinaus Richtlinien, um Ihre vorhandenen Entwicklungstools zu ändern, sodass sie weiterhin funktionieren, wenn Sie sie für Windows Store-apps ausführen.  Um diese Informationen zu verstehen, ist es am besten, wenn Sie mit der Common Language Runtime Profilerstellungs-API vertraut sind, Sie bereits diese API in ein Diagnosetool verwendet haben, dass die relevanten ausgeführt wird, ordnungsgemäß für die Windows-desktop-Anwendungen, und Sie jetzt beim Ändern des Tools für Windows Store-apps ordnungsgemäß ausgeführt wird.  
  
## <a name="introduction"></a>Einführung

 Wenn Sie es hinter dem einleitungsabsatz vorgenommen haben, können Sie mit der CLR-Profilerstellungs-API vertraut sind.  Sie haben bereits ein Diagnosetool geschrieben, die auch für verwaltete desktop-Anwendungen funktioniert.  Nachdem Sie neugierig sind, was zu tun ist, damit das Tool mit einer verwalteten Windows Store-app funktioniert.  Vielleicht haben Sie bereits versucht, diese Arbeit und festgestellt, dass es sich nicht um eine einfache Aufgabe ist.  Es gibt tatsächlich einige Aspekte, die möglicherweise nicht klar, alle Tools, die Entwickler.  Zum Beispiel:  
  
-   Windows Store-apps, die in einem Kontext mit stark eingeschränkten Berechtigungen ausgeführt werden.  
  
-   Windows-Metadatendateien weisen eindeutige Merkmale im Vergleich zu herkömmlichen verwalteten Module auf.  
  
-   Anhalten von sich selbst beim Ausfall von Interaktivität Gewohnheit haben, Windows Store-apps.  
  
-   Ihre prozessübergreifenden Kommunikationsmechanismen können aus verschiedenen Gründen nicht mehr funktionieren.  
  
 Dieses Thema enthält die Dinge, denen Sie achten müssen und wie richtig mit ihnen umgegangen.  
  
 Wenn Sie mit der CLR-Profilerstellungs-API vertraut sind, überspringen Sie auf die Ressourcen am Ende dieses Themas besser einführende Informationen zu finden.  
  
 Bereitstellen von Details zu bestimmten Windows-APIs und wie sie verwendet werden soll, ist auch außerhalb des Bereichs der in diesem Thema.  Erwägen Sie in diesem Thema einen Ausgangspunkt, und finden Sie in MSDN, um weitere Informationen zu jeder Windows-APIs, die auf die hier verwiesen wird.  
  
## <a name="architecture-and-terminology"></a>Architektur und-Terminologie

 In der Regel ist ein Diagnosetool eine Architektur wie in der folgenden Abbildung dargestellt. Er verwendet den Begriff "Profiler", aber viele Tools gehen weit über die normale Leistung oder profilerstellung in Bereiche z. B. Code Coverage, simulieren Objekt-Frameworks, Zeitreise Debuggen, die Anwendung überwachen und so weiter.  Der Einfachheit halber wird in diesem Thema weiterhin auf alle diese Tools als Profiler finden Sie unter.  
  
 In diesem Thema wird die folgende Terminologie verwendet:  
  
**Anwendung**

Dies ist die Anwendung, die der Profiler analysiert werden.  In der Regel ist der Entwickler der Anwendung nun den Profiler verwenden, zum Diagnostizieren von Problemen mit der Anwendung.  Klicken Sie in der Vergangenheit diese Anwendung wäre eine Windows-desktop-Anwendung, aber in diesem Thema betrachten wir Windows Store-apps.  
  
**Profiler-DLL**

Dies ist die Komponente, die lädt in den Prozessbereich der Anwendung analysiert wird.  Diese Komponente, auch bekannt als der Profiler "Agent" bezeichnet, implementiert die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2,3, usw.)-Schnittstellen und nutzt die [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2,3, usw.) Schnittstellen zum Sammeln von Daten über die Anwendung analysiert und möglicherweise ändern, die Aspekte des Verhaltens der Anwendung.  
  
**Profiler-Benutzeroberfläche**

Dies ist eine Desktopanwendung, der der Profiler-Benutzer interagiert.  Er ist verantwortlich für die Status der Anwendung dem Benutzer angezeigt und ermöglichen dem Benutzer die Möglichkeit zum Steuern des Verhaltens der Anwendung analysiert.  Diese Komponente wird immer im eigenen Prozessbereich, die getrennt von den Prozessbereich der Anwendung, die profilerstellung ausgeführt wird, ausgeführt.  Der Profiler-Benutzeroberfläche kann auch als "Anfügen des Triggers", die aufruft, wird die [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) Methode, um zu einem Anwendungsfehler analysiert der Profiler-DLL in diesen Fällen zu laden, in dem die Profiler-DLL nicht, geladen Sie beim Start werden.  
  
> [!IMPORTANT]
> Der Profiler-Benutzeroberfläche sollte eine Windows-desktop-Anwendung, bleiben, auch wenn es zu kontrollieren und Berichten in einer Windows Store-app verwendet wird.  Erwarten Sie nicht in der Lage, Packen und senden Ihre Tools "Diagnose" in der Windows Store.  Ihr Tool müsste führen Sie die Schritte, die Windows Store-apps nicht möglich, und viele Dinge in die Profiler-Benutzeroberfläche befinden.  
  
 In diesem Dokument wird im Beispielcode wird vorausgesetzt, dass:  
  
- Da sie eine systemeigene DLL, gemäß den Anforderungen von der CLR-Profilerstellungs-API muss, wird der Profiler-DLL in C++ geschrieben.  
  
- Der Profiler-Benutzeroberfläche ist in c# geschrieben.  Nicht Dies ist erforderlich, aber da keine Anforderungen für die Sprache für die Profiler-Benutzeroberfläche-Prozess gelten, Was spricht dagegen, wählen Sie eine Sprache, die präzise und einfach ist?  
  
### <a name="windows-rt-devices"></a>Windows RT-Geräte

Windows RT-Geräten sind sich Recht gesperrt.  Drittanbieter-Tools für die profilerstellung können nicht einfach auf solchen Geräten geladen werden.  Dieses Dokument konzentriert sich auf Windows 8-PCs.  
  
## <a name="consuming-windows-runtime-apis"></a>Nutzen die Windows-Runtime-APIs

 In eine Reihe von Szenarien, die in den folgenden Abschnitten erläutert werden soll muss die Profiler-UI-desktop-Anwendung einige neue Windows-Runtime-APIs nutzen.  Sie sollten in der Dokumentation, um zu verstehen, welche Windows-Runtime-APIs von desktop-Anwendungen verwendet werden kann, und, ob sich ihr Verhalten beim unterscheidet aufgerufen von desktopanwendungen und Windows Store apps.  
  
 Wenn der Profiler-Benutzeroberfläche in verwaltetem Code geschrieben ist, werden einige Schritte, die Sie tun, damit die Windows-Runtime-APIs einfach nutzen müssen.  Finden Sie unter den [verwaltete desktop-apps und Windows-Runtime](https://go.microsoft.com/fwlink/?LinkID=271858) Weitere Informationen.  
  
## <a name="loading-the-profiler-dll"></a>Laden die Profiler-DLL

 In diesem Abschnitt wird beschrieben, wie der Profiler-Benutzeroberfläche führt dazu, dass die Windows Store-app, um die Profiler-DLL zu laden.  Der Code in diesem Abschnitt beschriebenen gehört in der Profiler-Benutzeroberfläche-desktop-app und umfasst daher mithilfe von Windows-APIs, die für desktop-apps sicher, aber nicht unbedingt für Windows Store-apps sicher sind.  
  
 Der Profiler-Benutzeroberfläche kann dazu führen, dass der Profiler-DLL in den Prozessbereich der Anwendung, auf zwei Weisen geladen werden:  
  
-   Beim Start der Anwendung, wie durch Umgebungsvariablen gesteuert.  
  
-   Durch Anfügen an die Anwendung nach dem Start vollständig durchgeführt, durch den Aufruf wurde der [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) Methode.  
  
 Eines Ihrer ersten Hindernisse wird beim Start laden und Anfügen-Laden von der Profiler-DLL ordnungsgemäß mit Windows Store-apps funktioniert abgerufen werden.  Beide Formen des Ladevorgangs Freigeben von gemeinsamen einige Besonderheiten zu beachten, beginnen wir mit ihnen.  
  
### <a name="common-considerations-for-startup-and-attach-loads"></a>Allgemeine Überlegungen zum Starten und Anfügen von auslastungen

 **Signieren Sie Ihre Profiler-DLL**  
 Wenn Windows versucht, die der Profiler-DLL zu laden, überprüft er, dass der Profiler-DLL ordnungsgemäß signiert ist.  Wenn dies nicht der Fall ist, wird die Last ein Fehler auftritt, wird standardmäßig. Hierfür gibt es zwei Möglichkeiten:  
  
-   Stellen Sie sicher, dass der Profiler-DLL signiert wird.  
  
-   Teilen Sie Ihre Benutzer, dass sie eine Entwicklerlizenz auf ihrem Computer Windows 8 installieren müssen, bevor Sie mit dem Tool.  Dies kann automatisch von Visual Studio oder manuell über eine Eingabeaufforderung erfolgen.  Weitere Informationen finden Sie unter [Anfordern einer Entwicklerlizenz](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).  
  
 **Dateisystemberechtigungen**  
 Die Windows Store-app muss über die Berechtigung zum Laden und Ausführen der Profiler-DLL aus dem Speicherort im Dateisystem, in dem er sich befindet.  Standardmäßig die Windows Store-app verfügt nicht über diese Berechtigungen für die meisten Verzeichnisse, und jeder fehlerhafte Versuch, Ihr Profiler-DLL zu laden, erzeugt einen Eintrag im Ereignisprotokoll Windows-Anwendung, das in etwa wie folgt aussieht:  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 Windows Store-apps sind im Allgemeinen nur zulässig, auf eine begrenzte Anzahl von Speicherorten auf dem Datenträger zuzugreifen.  Jede Windows Store-app stehen einen eigenen Anwendungsordnern für Daten als auch einige andere Bereiche im Dateisystem für die alle Windows Store-apps Zugriff gewährt werden.  Es empfiehlt sich die Profiler-DLL und die zugehörigen Abhängigkeiten an einer beliebigen Stelle unter "Programme" oder "Program Files (x86), zu installieren, da alle Windows Store-apps verfügen über Lese- und es standardmäßig Ausführungsberechtigungen.  
  
### <a name="startup-load"></a>Beim Start laden

 In der Regel in einer desktop-app die Profiler-Benutzeroberfläche werden aufgefordert, eine Start-Auslastung mit der Profiler-DLL durch die Initialisierung eines Umgebungsblocks, der die erforderlichen Umgebungsvariablen für die CLR-Profilerstellungs-API enthält (d. h. `COR_PROFILER`, `COR_ENABLE_PROFILING`, und `COR_PROFILER_PATH`), und Klicken Sie dann erstellen einen neuen Prozess mit dieser Umgebungsblock.  Gleiches gilt für Windows Store-apps, jedoch sind die Mechanismen verschieden.  
  
 **Nicht mit erhöhten Rechten ausführen.**  
 Wenn verarbeiten sollte eine Versuche zum Erzeugen von Windows Store-app-Prozess B Prozess A auf mittlerer Integrität Ebene nicht mit hohe Integritätsstufe ausgeführt werden (die nicht erweitert wird).  Dies bedeutet, dass die Profiler-Benutzeroberfläche mit mittlerer Integritätsebene ausgeführt werden sollte, oder es muss eine andere desktop-Prozess mit mittlerer Integritätsebene, kümmert sich beim Starten der Windows Store-app erstellen.  
  
 **Auswählen einer Windows Store-App-Profil**  
 Zunächst sollten Sie Ihr Profiler Benutzer auffordern, welche Windows Store-app zu starten.  Für desktop-apps vielleicht würden Sie einen Datei-Dialogfeld "Durchsuchen" anzeigen, und der Benutzer suchen und wählen Sie eine .exe-Datei würde.  Aber Windows Store-apps unterschiedlich sind, und verwenden ein Dialogfeld "Durchsuchen" ist nicht sinnvoll.  Stattdessen ist es besser, die dem Benutzer eine Liste der für diesen Benutzer aus installierten Windows Store-apps anzuzeigen.  
  
 Sie können die [PackageManager-Klasse](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) zum Generieren dieser Liste.  `PackageManager` ist eine Windows-Runtime-Klasse, die desktop-apps zur Verfügung steht, und es ist tatsächlich *nur* für desktop-apps verfügbar.  
  
 Im folgenden Beispiel Ode eine hypothetische geschrieben als desktop-app in c# Yses Profiler-Benutzeroberfläche die `PackageManager` zum Generieren einer Liste mit den Windows-apps:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **Angeben der benutzerdefinierten Umgebungsblock**  
 Eine neue COM-Schnittstelle, [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), können Sie zum Anpassen des ausführungsverhaltens einer Windows Store-App, um einige Formen der Diagnose zu vereinfachen.  Einer der Methoden, [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), können Sie einen Umgebungsblock für die Windows Store-app übergeben werden, wenn er gestartet wird, sowie andere nützliche Effekte, z.B. das Deaktivieren von automatischen Prozess anhalten.  Der Umgebungsblock ist wichtig, denn das ist, in dem Sie die Umgebungsvariablen angeben müssen (`COR_PROFILER`, `COR_ENABLE_PROFILING`, und `COR_PROFILER_PATH)`) von der CLR verwendet wird, um die Profiler-DLL zu laden.  
  
 Betrachten Sie den folgenden Codeausschnitt aus:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 Es gibt einige Elemente, die Sie benötigen, um richtig zu machen:  
  
-   `packageFullName` kann bestimmt werden, und durchlaufen die Pakete und konturkreise per ziehbewegung `package.Id.FullName`.  
  
-   `debuggerCommandLine` ist ein wenig interessanter.  Um den Block benutzerdefinierte Umgebung für die Windows Store-app zu übergeben, müssen Sie Ihre eigenen vereinfachte dummy-Debugger zu schreiben.  Windows erzeugt die Windows Store-app angehalten, und klicken Sie dann Ihren Debugger starten Ihren Debugger mit einer Befehlszeile wie in diesem Beispiel zugeordnet:  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     wo `-p 1336` bedeutet, dass die Windows Store-app hat die Prozess-ID 1336, und `-tid 1424` bedeutet, dass Thread-ID 1424 ist der Thread, der angehalten wurde.  Ihre dummy Debugger würde der ThreadID, über die Befehlszeile zu analysieren, Fortsetzen von Threads und dann beendet.  
  
     Hier einige Beispiele für C++-Code zu diesem Zweck ist (Achten Sie darauf, fehlerüberprüfung hinzufügen!):  
  
    ```cpp  
    int wmain(int argc, wchar_t* argv[])  
    {      
        // …  
        // Parse command line here  
        // …  
  
        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME,   
                                                                  FALSE /* bInheritHandle */, nThreadID);  
        ResumeThread(hThread);  
        CloseHandle(hThread);  
        return 0;  
    }  
    ```  
  
     Sie müssen dieser dummy-Debugger als Bestandteil der Diagnose-Tool-Installation bereitstellen, und geben Sie dann den Pfad zu dieser Debugger in den `debuggerCommandLine` Parameter.  
  
 **Beim Starten der Windows Store-app**  
 Der Zeitpunkt, an die Windows Store-app zu starten ist schließlich eingetroffen. Wenn Sie sich bereits bereits versucht haben, tun dies selbst, Sie haben vielleicht festgestellt, die [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) ist, wie Sie einen Windows Store-app-Prozess nicht erstellen.  Stattdessen müssen Sie mit der [IApplicationActivationManager::ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) Methode.  Zu diesem Zweck müssen Sie die App-Benutzer-Modell-ID der Windows Store-app abzurufen, die Sie starten können.  Und dies bedeutet, dass Sie müssen ein wenig Schlüsseln über das Manifest.  
  
 Beim Durchlaufen von Paketen (finden Sie unter "Auswählen einer Windows Store-App zum Profil" in der [beim Start laden](#Startup) zuvor mithilfe des Abschnitts), sollten Sie den Satz der Anwendungen, die in das aktuelle Paket-Manifest enthalten abrufen:  
  
```csharp  
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";  
  
AppxPackaging.IStream manifestStream;  
SHCreateStreamOnFileEx(  
                    manifestPath,  
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE  
                    0,              // file creation attributes  
                    false,          // fCreate  
                    null,           // reserved  
                    out manifestStream);  
  
IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);  
  
IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();  
```  
  
 Ja, ein Paket kann mehrere Anwendungen, und jede Anwendung verfügt über eine eigene Anwendungsbenutzermodell-ID  Daher sollten Sie fordern Ihre Benutzer die Anwendung, und ziehen Sie die Anwendung Benutzer-Modell-ID aus der betreffenden Anwendung:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
    //...
}
```  
  
 Schließlich gibt es jetzt benötigen Sie für die Windows Store-app zu starten:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **Denken Sie daran, DisableDebugging aufrufen**  
 Wenn Sie aufgerufen wird, [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), vorgenommenen eine Zusicherung, die durch den Aufruf hinter sich aufzuräumen würde die [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) -Methode, seien Sie sicher, dass Sie Wenn die Profilerstellungssitzung wird über.  
  
### <a name="attach-load"></a>Fügen Sie laden

 Wenn möchte, dass die Profiler-Benutzeroberfläche die Profiler-DLL zu einer Anwendung anfügen, die bereits gestartet wurde, ausgeführt wird, verwendet es [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md).  Dasselbe gilt für Windows Store-apps.  Aber stellen Sie sicher, dass neben den allgemeinen Überlegungen, die weiter oben aufgeführt, die Ziel-Windows Store-app wird nicht angehalten.  
  
 **EnableDebugging**  
 Wie bei beim Start laden, rufen Sie die [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) Methode.  Für die Übergabe eines Umgebungsblocks nicht erforderlich, aber Sie benötigen einen der anderen Features: Deaktivieren von automatischen Prozess anhalten.  Wenn der Profiler-Benutzeroberfläche aufruft, andernfalls [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), die Ziel-Windows Store-app zu unterbrechen.  In der Tat ist dies wahrscheinlich, wenn der Benutzer ist jetzt mit der Profiler-Benutzeroberfläche interagiert, und die Windows Store-app nicht aktiv auf einem der Bildschirme, des Benutzers ist.  Und wenn die Windows Store app angehalten wird, es nicht auf eine reagieren kann zu signalisieren, dass die CLR an ihn sendet, die Profiler-DLL angefügt.  
  
 Daher sollten Sie Folgendes:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 Dies ist der gleiche Aufruf, die, den Sie für den Fall beim Start laden, außer Sie nicht, dass ein Debugger-Befehlszeile oder einem Umgebungsblock angeben machen würden.  
  
 **DisableDebugging**  
 Wie immer, vergessen Sie nicht, rufen Sie [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) Abschluss der Profilerstellungssitzung.  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>In der Windows Store-app ausgeführt wird  
 Daher hat die Windows Store-app zum Schluss die Profiler-DLL geladen.  Nachdem der Profiler-DLL Gewusst wie: Wiedergeben von den verschiedenen Regeln, die Windows Store-apps erforderlich eines besseren belehrt werden muss, reduziert, einschließlich der APIs zulässig sind und Ausführung von mit Berechtigungen.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Bleiben Sie auf die Windows Store-app-APIs  
 Während Sie die Windows-API navigieren, sehen Sie sich, dass jede API dokumentiert ist, als desktop-apps, Windows Store-apps oder beide gilt.  Z. B. die **Anforderungen** Abschnitt der Dokumentation für die [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) -Funktion zeigt an, dass die Funktion für desktop-apps gilt. Im Gegensatz dazu die [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) -Funktion steht für desktop-apps und Windows Store-apps.  
  
 Wenn Sie die Profiler-DLL zu entwickeln, behandelt, als ob es sich um eine Windows Store-app ist und nur APIs, die je nach Verfügbarkeit für Windows Store-apps beschrieben werden.  Analysieren Sie Ihre Abhängigkeiten (Sie können z. B. ausführen `link /dump /imports` für die Profiler-DLL zu überwachen), und suchen Sie dann auf die Dokumentation finden Sie unter dem Ihre Abhängigkeiten in Ordnung sein, und die nicht.  In den meisten Fällen können Ihr Verstöße gegen diese durch eine neuere Form der API, die als sicher dokumentiert ist einfach ersetzt werden behoben werden (z. B. ersetzen [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) mit [ InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).  
  
 Sie werden feststellen, dass die Profiler-DLL aufruft, einige APIs, die für desktop-apps gelten, und sie anscheinend noch funktionieren, auch wenn der Profiler-DLL in einer Windows Store-app geladen wird.  Achten Sie darauf, dass es riskant, verwenden Sie eine beliebige API zur Verwendung mit Windows Store-apps in der Profiler-DLL beim Laden in eine Windows Store-app-Prozess nicht dokumentiert ist:  
  
-   Diese APIs sind nicht garantiert, funktionieren, wenn die im eindeutigen Kontext aufgerufen wird, die Windows Store-apps in ausgeführt.  
  
-   Diese APIs funktionieren möglicherweise nicht konsistent, wird von verschiedenen Prozessen von Windows Store-app aufgerufen.  
  
-   Diese APIs von Windows Store-apps in der aktuellen Version von Windows, gut zu funktionieren scheint jedoch möglicherweise unterbrochen oder in zukünftigen Versionen von Windows deaktiviert werden.  
  
 Am besten ist, beheben Sie alle Ihre Verstöße und das Risiko zu vermeiden.  
  
 Möglicherweise, dass Sie absolut nicht ohne eine bestimmte API und nicht werden einen Ersatz für Windows Store-apps geeignet ist gefunden können.  In diesem Fall mindestens:  
  
-   Testen, zu testen, die dynamisches Daylights aus Ihrer Nutzung dieser API zu testen.  
  
-   Beachten Sie, dass die API möglicherweise plötzlich unterbrochen oder nicht mehr angezeigt, wenn Sie aufgerufen wird von in Windows Store apps in zukünftigen Versionen von Windows.  Dies wird nicht berücksichtigt werden ein Problem für die Kompatibilität von Microsoft, und unterstützen Ihre Nutzung davon werden sich nicht auf eine Priorität.  
  
### <a name="reduced-permissions"></a>Verringerten Berechtigungen

 Es ist außerhalb des Bereichs der in diesem Thema, um alle Möglichkeiten aufzulisten, die Berechtigungen für Windows Store-app von desktop-apps unterscheiden.  Aber sicherlich das Verhalten unterscheiden sich jedes Mal, wenn der Profiler-DLL (Wenn in einer Windows Store-app im Vergleich zu einer desktop-app geladen wird) versucht, den Zugriff auf Ressourcen.  Das Dateisystem ist das häufigste Beispiel.  Es gibt jedoch einige wenige platziert werden, auf dem Datenträger, die eine bestimmte Windows Store-app zugreifen darf (finden Sie unter [Datei Zugriff und Berechtigungen (Windows-Runtime-apps](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), und die Profiler-DLL denselben Einschränkungen unterliegt.  Testen Sie Ihren Code gründlich.  
  
### <a name="inter-process-communication"></a>Prozessübergreifende Kommunikation

 Wie in der Abbildung am Anfang dieses Artikels dargestellt, müssen die Profiler-DLL (geladen in den Prozessbereich der Windows Store-app) wahrscheinlich mit der Profiler-Benutzeroberfläche (auf einer separaten desktop-app-Prozess-Adressbereich) durch Ihre eigenen benutzerdefinierten prozessübergreifende Kommunikation Kommunikation (IPC)-Kanal.  Der Profiler-Benutzeroberfläche sendet Signale, an die Profiler-DLL für ihr Verhalten zu ändern und die Profiler-DLL sendet Daten aus der analysierten Windows Store-app zurück in die Profiler-Benutzeroberfläche für die Nachbearbeitung und für den Benutzer Profiler anzeigen.  
  
 Die meisten Profiler müssen auf diese Weise funktionieren, aber die Optionen für die IPC-Mechanismen sind stärker eingeschränkt, wenn der Profiler-DLL in einer Windows Store-app geladen wird.  Benannte Pipes sind z. B. nicht Teil der Windows Store-app-SDK, damit Sie sie nicht verwenden können.  
  
 Natürlich bleiben jedoch weiterhin in, wenn auch in eingeschränkter Weise.  Ereignisse sind ebenfalls verfügbar.  
  
 **Kommunikation über Dateien**  
 Den größten Teil Ihrer Daten werden wahrscheinlich über Dateien zwischen dem Profiler-DLL und die Profiler-Benutzeroberfläche übergeben.  Der Schlüssel ist, wählen Sie einen Speicherort für die Datei, die sowohl die Profiler-DLL (im Kontext einer Windows Store-App) als auch die Profiler-Benutzeroberfläche gelesen haben und Schreibzugriff auf.  Z. B. der Pfad des temporären Ordners ist ein Speicherort, den sowohl die Profiler-DLL als auch die Profiler-Benutzeroberfläche zugreifen können, aber keine anderen Windows Store-app-Paket kann zuzugreifen (also alle Informationen, die Sie von anderen Windows Store-app-Pakete protokollieren Schutz).  
  
 Sowohl die Profiler-Benutzeroberfläche als auch die Profiler-DLL können diesen Pfad unabhängig ermitteln.  Der Profiler-Benutzeroberfläche beim durchlaufen alle Pakete, die für den aktuellen Benutzer installiert (Siehe den Beispielcode weiter oben), erhält Zugriff auf die `PackageId` -Klasse, aus dem der Pfad des temporären Ordners mit Code wie diesen Codeausschnitt abgeleitet werden kann.  (Wie immer ist fehlerüberprüfung aus Gründen der Übersichtlichkeit weggelassen.)  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 In der Zwischenzeit die Profiler-DLL können im Grunde das gleiche tun, wenn möglich mehr einfach erhalten Sie zu der ["applicationData"](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) Klasse, indem die [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) Eigenschaft.  
  
 **Über Ereignisse kommunizieren**  
 Gegebenenfalls einfach Signalisierung Semantik zwischen Ihrem Profiler-Benutzeroberfläche und die Profiler-DLL können Sie Ereignisse in Windows Store-apps als auch desktop-apps.  
  
 Sie können einfach aufrufen, über die Profiler-DLL, die [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) Funktion, um ein benanntes Ereignis mit einem beliebigen Namen erstellen, wie Sie.  Zum Beispiel:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 Der Profiler-Benutzeroberfläche muss dieses benannte Ereignis unter der Windows Store-app Namespace zu suchen.  Beispielsweise können die Profiler-Benutzeroberfläche aufrufen [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), den Ereignisnamen als angeben  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>` ist der Windows Store-app-AppContainer-SID.  Weiter oben in diesem Thema wurde gezeigt, wie die für den aktuellen Benutzer installierten Pakete durchlaufen werden.  Aus diesem Beispielcode können Sie die Paket-ID abrufen.  Und aus der Paket-ID, Sie erhalten die `<acSid>` mit ähnlich dem folgenden Code:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
### <a name="no-shutdown-notifications"></a>Keine Shutdown-Benachrichtigungen

 Wenn in einer Windows Store-app ausgeführt wird, die Profiler-DLL nicht empfehlenswert entweder [ICorProfilerCallback:: Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) oder sogar [DllMain](/windows/desktop/Dlls/dllmain) (mit `DLL_PROCESS_DETACH`) wird aufgerufen, um die Profiler-DLL zu benachrichtigen. dass die Windows Store-app beendet wird.  Tatsächlich sollten Sie erwarten, dass sie niemals aufgerufen werden.  In der Vergangenheit haben viele Profiler-DLLs verwendet diese Benachrichtigungen als praktische stellen, um Caches auf den Datenträger, Dateien zu schließen, Senden von Benachrichtigungen an die Profiler-Benutzeroberfläche usw. zu leeren.  Aber jetzt die Profiler-DLL muss ein wenig anders angeordnet werden.  
  
 Der Profiler-DLL muss Protokollieren von Informationen, wie es geht.  Aus Leistungsgründen empfiehlt es sich um batch-Informationen im Arbeitsspeicher und leeren sie auf die Festplatte als Batch über einen Schwellenwert hinaus dem Wachstum.  Jedoch wird davon ausgegangen, dass alle Informationen, die noch nicht auf den Datenträger geleert verloren gehen kann.  Dies bedeutet, Sie sollten mit Bedacht wählen Sie den Schwellenwert und, dass die Profiler-Benutzeroberfläche mit verstärkter Sicherheit für den Umgang mit unvollständigen Informationen, die von der Profiler-DLL geschrieben werden muss.  
  
## <a name="windows-runtime-metadata-files"></a>Windows-Runtime-Metadaten-Dateien

 Es ist über den Rahmen dieses Dokuments im Detail auf welche Windows-Runtime-Metadaten (WinMD) Dateien befinden.    In diesem Abschnitt ist auf die CLR-Profilerstellungs-API wie reagiert, wenn WinMD-Dateien von der Windows Store-app geladen werden, die der Profiler-DLL zu analysieren, ist begrenzt.  
  
### <a name="managed-and-non-managed-winmds"></a>Verwaltete und nicht verwaltete WinMDs

 Wenn ein Entwickler, der von Visual Studio zum Erstellen eines neuen Projekts für Windows-Runtime-Komponente verwendet wird, erzeugt ein Build dieses Projekts eine WinMD-Datei, die beschreibt, die Metadaten (die typenbeschreibungen von Klassen, Schnittstellen usw.), die vom Entwickler erstellt.  Wenn dieses Projekt einer verwalteten Sprache-Projekt in c# oder VB geschrieben ist, enthält der gleichen WinMD-Datei auch die Implementierung dieser Typen (d. h., die sie alle den IL-Code kompiliert, die aus dem Quellcode des Entwicklers enthält).  Solche Dateien werden als verwaltete WinMD-Dateien bezeichnet.  Sie sind interessant, darin, dass sie sowohl Windows-Runtime-Metadaten als auch die zugrunde liegende Implementierung enthalten.  
  
 Im Gegensatz dazu, wenn ein Entwickler eine Windows-Runtime-Komponentenprojekt für C++ erstellt wird, wird ein Build dieses Projekts erzeugt eine WinMD-Datei, die nur Metadaten enthält, und die Implementierung in einer separaten systemeigene DLL kompiliert wird.  Entsprechend enthalten die WinMD-Dateien, die im Windows SDK enthalten sind nur die Metadaten, mit der Implementierung in separaten systemeigenen DLLs, die mitgeliefert werden als Teil des Windows kompiliert.  
  
 Die folgenden Informationen gelten sowohl verwaltete WinMDs, die Metadaten als auch Implementierung enthalten, und nicht verwaltete WinMDs, die nur Metadaten enthalten.  
  
### <a name="winmd-files-look-like-clr-modules"></a>WinMD-Dateien sehen, wie CLR-Modulen

 Als die CLR geht, sind alle WinMD-Dateien Module an.  Die CLR-Profilerstellungs-API weist daher die Profiler-DLL beim Laden der WinMD-Dateien und was ihre ModuleIDs, auf die gleiche Weise wie für andere verwaltete Module sind.  
  
 Der Profiler-DLL können WinMD-Dateien aus anderen Modulen zu unterscheiden, durch den Aufruf der [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) -Methode, und Überprüfen der `pdwModuleFlags` output-Parameter für die [COR_PRF_MODULE_WINDOWS_ Common Language RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) Flag.  (Es wird festgelegt nur, wenn die Modul-ID ein WinMD darstellt.)  
  
### <a name="reading-metadata-from-winmds"></a>Lesen von Metadaten aus WinMDs

 WinMD-Dateien, wie bei regulären Modulen enthalten Metadaten, die über gelesen werden, kann die [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).  Allerdings ordnet die CLR Windows-Runtime-Typen in .NET Framework-Typen, wenn er, dass die WinMD-Dateien liest, damit Entwickler, die in verwaltetem Code programmieren, und nutzen die WinMD-Datei eine natürliche programmiererfahrung haben.  Einige Beispiele für diese Zuordnungen, finden Sie unter [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).  
  
 Also welche Ansicht Ihres Profilers erhalten, wenn die Metadaten-APIs verwendet: die Rohdatenansicht des Windows-Runtime und die zugeordneten .NET Framework-Ansicht?  Die Antwort: Es liegt an Ihnen.  
  
 Beim Aufrufen der [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) Methode für eine winmd handelt, erhalten eine Schnittstelle für die Metadaten, wie z. B. [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), Sie können auch festlegen [OfNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)in die `dwOpenFlags` Parameter, um diese Zuordnung deaktivieren.  Andernfalls wird standardmäßig die Zuordnung aktiviert werden.  In der Regel wird ein Profiler die Zuordnung aktiviert ist, speichern, sodass die Zeichenfolgen, die der Profiler-DLL von den WinMD-Metadaten (z. B. Namen von Typen) erhält vertraut und natürlich für den Profiler-Benutzer sehen.  
  
### <a name="modifying-metadata-from-winmds"></a>Ändern der Metadaten von WinMDs

 Ändern der Metadaten in WinMDs wird nicht unterstützt.  Aufrufen der [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) -Methode für ein WinMD-Datei, und geben Sie [OfWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) in die `dwOpenFlags` Parameter, oder bitten Sie z. B. für eine beschreibbare Metadatenschnittstelle [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) schlägt fehl.  Dies ist von besonderer Bedeutung an Profiler mit IL-Code umschreiben, die die Metadaten zur Unterstützung von ihre Instrumentation (z. B. AssemblyRefs oder neue Methoden hinzufügen) zu ändern.  Damit Sie überprüfen sollten [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) zuerst (wie im vorherigen Abschnitt beschrieben) und nicht für schreibbare Metadatenschnittstellen auf solcher Module auffordern.  
  
### <a name="resolving-assembly-references-with-winmds"></a>Auflösen von Assemblyverweisen mit WinMDs

 Viele Profiler müssen zum Auflösen von Verweisen auf Metadaten manuell, um mit Instrumentation oder typenüberprüfung zu erleichtern.  Solche Profiler müssen zu beachten, wie die CLR Assemblyverweise, die auf WinMDs, verweisen auflöst, da diese Verweise in eine ganz neue Weise als standardmäßige Assemblyverweise aufgelöst werden.  
  
## <a name="memory-profilers"></a>Arbeitsspeicher-Profiler

 Der Garbage Collector und den verwalteten Heap sind nicht grundlegend in einer Windows Store-app und einer desktop-app.  Es gibt jedoch einige feine Unterschiede, denen Entwickler von Profilern berücksichtigen müssen.  
  
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC erstellt einen verwalteten thread

 Bei der profilerstellung erstellt der Profiler-DLL in der Regel einen separaten Thread aus dem Aufrufen der [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) Methode.  Dies ist nichts Neues.  Aber was überraschend ist, dass das Act über den Status einer Garbagecollection in einer Windows Store-app Ihr Thread in einen verwalteten Thread umwandeln kann (z. B. ThreadID-API-Profilerstellung wird für diesen Thread erstellt werden).  
  
 Um die Konsequenzen, dies zu verstehen, ist es wichtig, die Unterschiede zwischen synchronen und asynchronen Aufrufe zu verstehen, wie in der CLR-Profilerstellungs-API definiert. Beachten Sie, dass dies das Konzept von asynchronen Aufrufen in Windows Store-apps ganz anders ist.  Finden Sie im Blogbeitrag [warum wir CORPROF_E_UNSUPPORTED_CALL_SEQUENCE haben](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) für Weitere Informationen.  
  
 Der relevante Punkt ist, dass Aufrufe, die auf die Threads, die vom Profiler erstellt immer synchron, betrachtet werden, auch wenn diese Aufrufe von außerhalb eine Implementierung eines der Profiler-DLL erfolgen [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Methoden.  Oder zumindest, verwendet der Fall.  Nun, dass die CLR aufgrund von den Aufruf des Profilers Thread in einen verwalteten Thread aktiviert hat [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), dass Thread Ihres Profilers Thread nicht mehr berücksichtigt wird.  Daher ist es möglich, den die CLR erzwingt eine strengere Definition für diesen Thread als synchrone wodurch – nämlich, die ein Aufruf von stammen muss in einem der Profiler-DLL [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Methoden wie synchrone qualifizieren.  
  
 Was bedeutet dies in der Praxis?  Die meisten [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Methoden sind nur sicher synchron aufgerufen werden und wird andernfalls sofort fehlschlagen.  Wenn der Profiler-DLL verwendet Ihre [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) Thread für anderer Aufrufe, die in der Regel in Profiler erstellte Threads (z. B. [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), oder [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)), also Probleme auftreten.  Auch eine asynchrone Safe-Funktion, z. B. [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) verfügt über spezielle Regeln, wenn Sie von verwalteten Threads aufgerufen. (Finden Sie im Blogbeitrag [Profiler Stack walking: Grundlagen und darüber hinaus](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) für Weitere Informationen.)  
  
 Daher wird empfohlen, die einen beliebigen Thread mit der Profiler-DLL erstellt wird, zum Aufrufen von [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) sollte verwendet werden, *nur* für GCs ausgelöst und der Antwort auf die GC-Rückrufe.  Sie sollte nicht in der Profilerstellungs-API für andere Aufgaben wie Stack sampling oder Trennen von aufrufen.  
  
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences

 Ab .NET Framework 4.5, es gibt ein neuer GC-Rückruf, [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), die Einblicke, die der Profiler Weitere Informationen über vollständige *abhängigen Handles*. Diesen Steuerpunkten fügen einen Verweis effektiv von einem Quellobjekt in ein Zielobjekt im Rahmen der GC Prozesslebensdauer-Verwaltung.  Abhängigen Handles sind nichts neues, und Entwickler, die in verwaltetem Code Programmieren konnten ihre eigenen abhängigen Handles erstellen, indem die <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> Klasse noch bevor Windows 8 und .NET Framework 4.5.  
  
 Verwaltete XAML Windows Store-apps stellen Sie jedoch jetzt intensiven Gebrauch von abhängigen Handles.  Insbesondere werden die CLR, die diese unterstützen bei der Verwaltung von Verweiszyklen zwischen verwalteten Objekten und nicht verwaltete Windows-Runtime-Objekte verwendet.  Dies bedeutet, dass es wichtiger als je zuvor für Arbeitsspeicher-Profiler, der diese abhängigen Handles informiert zu werden, damit sie zusammen mit dem Rest der Kanten im Diagramm Heap visualisiert werden können.  Der Profiler-DLL verwenden, sollten [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), und [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) zusammen, um eine vollständige Übersicht über das Diagramm Heap bilden. .  
  
## <a name="conclusion"></a>Schlussbemerkung

 Es ist möglich, die CLR-Profilerstellungs-API verwenden, um in Windows Store-apps ausgeführten, verwalteten Code zu analysieren.  Sie können in der Tat nehmen eine vorhandene Profiler, die Sie entwickeln, und einige bestimmten Änderungen vornehmen, damit, dass sie Windows Store-apps als Ziel verwenden kann.   Der Profiler-Benutzeroberfläche sollten die neuen APIs verwenden, für das Aktivieren der Windows Store-app im Debugmodus.  Stellen Sie sicher, dass der Profiler-DLL die APIs für Windows Store-apps verwendet.  Der Kommunikationsmechanismus zwischen Ihrem Profiler-DLL und die Profiler-Benutzeroberfläche muss mit den Windows Store-app-API-Einschränkungen Bedenken und Bewusstsein für die eingeschränkten Berechtigungen vorhanden, die für Windows Store-apps geschrieben werden.  Der Profiler-DLL muss beachten wie die CLR WinMDs behandelt, und wie der Garbage Collector Verhalten in Bezug auf die verwalteten Threads unterscheidet.  
  
## <a name="resources"></a>Ressourcen

 **Die Common Language Runtime**  
 -   [CLR Profiling-API-Referenz](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [CLR-Metadaten-API-Referenz](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Der CLR Interaktion mit der Windows-Runtime**  
 [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
  
 **Windows Store-Apps**  
 -   [Zugriff auf Dateien und Berechtigungen (Windows-Runtime-apps](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [Anfordern einer Entwicklerlizenz](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [IPackageDebugSettings-Schnittstelle](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>Siehe auch

[Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)  
