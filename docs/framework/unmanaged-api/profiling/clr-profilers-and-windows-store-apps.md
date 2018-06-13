---
title: CLR-Profiler und den Windows Store-Apps
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
ms.openlocfilehash: 20a1ed9b6b613b1e4d3e5363ab9995cc81295091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462285"
---
# <a name="clr-profilers-and-windows-store-apps"></a>CLR-Profiler und den Windows Store-Apps
Dieses Thema bietet eine Übersicht zu bedenken, wenn das Schreiben von Diagnosetools, die Analyse von verwaltetem Code, die innerhalb einer Windows Store-Apps ausgeführt wird.  Darüber hinaus Richtlinien, um Ihre vorhandenen Entwicklungstools zu ändern, sodass bei der Ausführung für Windows Store-apps funktionieren weiterhin.  Um diese Informationen zu verstehen, ist es am besten, wenn Sie mit der Common Language Runtime Profiling-API vertraut sind, Sie bereits diese API in ein Diagnosetool verwendet haben, dass ausgeführt wird, ordnungsgemäß für Windows-desktopanwendungen, und Sie jetzt interessiert sind, ändern Sie das tool für Windows Store-apps ordnungsgemäß ausgeführt wird.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
 [Introduction (Einführung)](#Intro)  
 [Architektur und Terminologie](#Arch)  
 [Windows RT-Geräte](#RT)  
[Nutzen die Windows-Runtime-APIs](#Consuming)  
[Laden die Profiler-DLL](#Loading)  
 [Allgemeine Überlegungen für den Start und lädt Anfügen](#Common)  
 [Start laden](#Startup)  
 [Fügen Sie laden](#Attach)  
[Innerhalb der Windows Store-app ausgeführt wird](#Running)  
 [Halten Sie die Windows Store-app-APIs](#APIs)  
 [Verringerten Berechtigungen](#Permissions)  
 [Prozessübergreifende Kommunikation](#Interprocess)  
 [Keine Benachrichtigung zum Herunterfahren](#Shutdown)  
[Windows-Runtime-Metadatendateien](#Metadata)  
 [Verwaltete und nicht verwaltete WinMDs](#WMDs)  
 [WinMD-Dateien Aussehen von CLR-Module](#CLRModules)  
 [Lesen von Metadaten aus WinMDs](#Reading)  
 [Ändern von Metadaten aus WinMDs](#Modifying)  
 [Auflösen von Assemblyverweisen mit WinMDs](#Resolving)  
[Arbeitsspeicher-Profiler](#Profilers)  
 [ForceGC erstellt einen verwalteten thread](#ForceGC)  
 [ConditionalWeakTableReferences](#WeakTable)  
[Schlussfolgerung](#Conclusion)  
[Ressourcen](#Resources)  
  
<a name="Intro"></a>   
## <a name="introduction"></a>Einführung  
 Wenn Sie es hinter dem einführenden Abschnitt vorgenommen haben, können Sie mit der CLR Profiling-API vertraut.  Sie haben bereits ein Diagnosetool geschrieben, die auch für verwaltete desktop-Anwendungen funktioniert.  Nachdem Sie wissen möchten, was zu tun, damit das Tool mit einer verwalteten Windows Store-app funktioniert.  Vielleicht haben Sie bereits versucht, diese Arbeit, und haben festgestellt, dass es sich nicht um eine einfache Aufgabe ist.  Es gibt tatsächlich einige Aspekte, die möglicherweise nicht alle Tools Entwicklern offensichtlich.  Zum Beispiel:  
  
-   Windows Store-apps werden in einem Kontext mit stark eingeschränkten Berechtigungen ausgeführt.  
  
-   Windows-Metadatendateien über eindeutige Merkmale, die im Vergleich zu herkömmlichen verwaltete Module verfügen.  
  
-   Windows Store-apps haben eine gewöhnen sich selbst anhalten, wenn Interaktivität ausfällt.  
  
-   Die Kommunikation zwischen Prozessen Mechanismen können aus verschiedenen Gründen nicht mehr funktionieren.  
  
 Dieses Thema enthält die Dinge, denen Sie berücksichtigen müssen und wie Sie ordnungsgemäß behandeln.  
  
 Wenn Sie auf die CLR Profiling-API vertraut sind, fahren Sie auf die Ressourcen am Ende dieses Themas finden Sie eine bessere Leistung einführende Informationen.  
  
 Bereitstellen von bis zu einem bestimmten Windows-APIs und wie sie verwendet werden soll, ist auch außerhalb des Bereichs der in diesem Thema.  Erwägen Sie in diesem Thema als Ausgangspunkt und verweisen auf MSDN erfahren Sie mehr über keine Windows-APIs auf die hier verwiesen wird.  
  
<a name="Arch"></a>   
## <a name="architecture-and-terminology"></a>Architektur und Terminologie  
 In der Regel ist ein Diagnosetool eine Architektur, wie in der folgenden Abbildung dargestellt. Es wird mit dem Begriff "Profiler", jedoch auch viele solche Tools über normale Leistung oder Arbeitsspeicher profiling in Bereiche wie z. B. Code Coverage modellieren Objekt Frameworks, Zeitreise Debuggen, Anwendung überwachen und so weiter.  In diesem Thema werden der Einfachheit halber weiterhin auf alle diese Tools als Profiler finden Sie unter.  
  
 In diesem Thema wird die folgende Terminologie verwendet:  
  
 Application  
 Dies ist die Anwendung, die der Profiler analysiert wird.  In der Regel wird der Entwickler der Anwendung nun den Profiler verwenden, zur Diagnose von Problemen mit der Anwendung.  In der Regel, diese Anwendung wäre ein Windows-Desktopanwendung, aber in diesem Thema wird Windows Store-apps sehen.  
  
 Profiler-DLL  
 Dies ist die Komponente, die lädt in den Prozessbereich der Anwendung analysiert wird.  Diese Komponente, auch bekannt als der Profiler "Agent" implementiert den [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2,3, usw.)-Hostingschnittstellen und nutzt die [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2,3, usw.) Schnittstellen zum Sammeln von Daten zur Anwendung analysiert und möglicherweise ändern, die Aspekte des Verhaltens der Anwendung.  
  
 Profiler-Benutzeroberfläche  
 Dies ist eine Desktopanwendung, der der Profiler-Benutzer mit interagiert.  Es ist für den Status der Anwendung dem Benutzer angezeigt, und erteilen dem Benutzer die Möglichkeit zum Steuern des Verhaltens der analysierten Anwendung verantwortlich.  Diese Komponente wird immer im eigenen Prozessbereich getrennt von den Prozessbereich der profilierten Anwendung ausgeführt.  Der Profiler-UI kann auch als "Anfügen des Triggers", die aufgerufen wird die [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) Methode, um zu einem Anwendungsfehler analysiert der Profiler-DLL in diesen Fällen zu laden, in dem die Profiler-DLL nicht, Beim Start geladen Sie werden.  
  
> [!IMPORTANT]
>  Die Profiler-Benutzeroberfläche sollte eine Windows-Desktopanwendung bleiben, selbst wenn er Steuerelement und Berichte auf einer Windows Store-app verwendet wird.  Erwarten Sie nicht in der Lage zu packen und senden Ihre Diagnosetool im Windows Store.  Das Tool muss Aktionen, die Windows Store-apps ist nicht möglich, und viele Dinge befinden sich in die Profiler-Benutzeroberfläche.  
  
 In diesem Dokument wird im Beispielcode vorausgesetzt, dass:  
  
-   Da sie eine systemeigene DLL, gemäß den Anforderungen der CLR Profiling-API muss, wird der Profiler-DLL in C++ geschrieben.  
  
-   Die Profiler-Benutzeroberfläche ist in c# geschrieben.  Nicht Dies ist erforderlich, aber da es keine Anforderungen für die Sprache für die Profiler-Benutzeroberfläche Prozess bestehen, warum nicht, wählen Sie eine Sprache, die präzise und übersichtlich ist?  
  
<a name="RT"></a>   
### <a name="windows-rt-devices"></a>Windows RT-Geräte  
 Windows RT-Geräte sind sehr gesperrt.  Drittanbieter-Profiler können nicht einfach auf solchen Geräten geladen werden.  Dieses Dokument konzentriert sich auf Windows 8-PCs.  
  
<a name="Consuming"></a>   
## <a name="consuming-windows-runtime-apis"></a>Nutzen die Windows-Runtime-APIs  
 In eine Reihe von Szenarien, die in den folgenden Abschnitten erläutert muss die Profiler-UI-desktop-Anwendung einige neue Windows-Runtime-APIs nutzen.  Sie sollten in der Dokumentation, um zu verstehen, welche Windows-Runtime-APIs von desktopanwendungen verwendet werden kann, und, ob ihr Verhalten beim unterscheidet aufgerufen von desktopanwendungen und Windows Store apps.  
  
 Wenn der Profiler-Benutzeroberfläche in verwaltetem Code geschrieben ist, werden einige Schritte, die Sie benötigen, zu tun, damit diese Windows-Runtime-APIs einfach nutzen.  Finden Sie unter der [verwaltete desktop-apps und Windows-Runtime](http://go.microsoft.com/fwlink/?LinkID=271858) Artikel finden Sie weitere Informationen.  
  
<a name="Loading"></a>   
## <a name="loading-the-profiler-dll"></a>Laden die Profiler-DLL  
 In diesem Abschnitt wird beschrieben, wie die Profiler-Benutzeroberfläche führt dazu, dass die Windows Store-app, um die Profiler-DLL zu laden.  Der Code in diesem Abschnitt beschriebenen gehört in der Profiler-UI-desktop-app und aus diesem Grund müssen Sie mit dem Windows-APIs, die für desktop-apps sicher aber nicht notwendigerweise für Windows Store-apps sicher sind.  
  
 Die Profiler-Benutzeroberfläche können dazu führen, dass die Profiler-DLL in den Prozessbereich der Anwendung, auf zwei Weisen geladen werden soll:  
  
-   Beim Start der Anwendung, da von Umgebungsvariablen gesteuert.  
  
-   Durch das Anfügen an die Anwendung, nachdem der Startvorgang abgeschlossen wurde, durch Aufrufen der [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) Methode.  
  
 Eine Ihrer ersten Hindernisse wird Start laden und fügen Sie laden die Profiler-DLL ordnungsgemäß mit Windows Store-apps abrufen.  Bei beiden Formen des Ladevorgangs einige Besonderheiten gemeinsam verwenden, beginnen wir also mit ihnen.  
  
<a name="Common"></a>   
### <a name="common-considerations-for-startup-and-attach-loads"></a>Allgemeine Überlegungen für den Start und lädt Anfügen  
 **Signieren Sie die Profiler-DLL**  
 Wenn Windows versucht, die Profiler-DLL zu laden, überprüft er, dass die Profiler-DLL ordnungsgemäß signiert ist.  Wenn dies nicht der Fall ist, wird die Last, die standardmäßig schlägt fehl. Hierfür gibt es zwei Möglichkeiten:  
  
-   Stellen Sie sicher, dass die Profiler-DLL signiert wird.  
  
-   Teilen Sie Ihre Benutzer, dass sie Bezug einer Entwicklerlizenz auf ihre Windows 8-Computer installieren müssen, bevor Sie das Tool verwenden.  Dies kann automatisch von Visual Studio oder manuell von einer Befehlszeile aus erfolgen.  Weitere Informationen finden Sie unter [Anfordern einer Entwicklerlizenz](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).  
  
 **Dateisystemberechtigungen**  
 Windows Store-app benötigen die Berechtigung zum Laden und Ausführen der Profiler-DLL aus dem Speicherort im Dateisystem, in dem er sich befindet.  Wird standardmäßig die Windows Store-app verfügt nicht über solche Berechtigungen für die meisten Verzeichnisse und alle Fehler beim Laden der Profiler-DLL erzeugt einen Eintrag in der Windows-Anwendungsereignisprotokoll, das etwa wie folgt aussieht:  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 Windows Store-apps sind im Allgemeinen nur zulässig, um eine begrenzte Anzahl von Positionen auf dem Datenträger zuzugreifen.  Jede Windows Store-app kann eine eigene Anwendungsordnern für Daten als auch einige andere Bereiche im Dateisystem zugreifen für die alle Windows Store-apps Zugriff gewährt werden.  Es wird empfohlen, die der Profiler-DLL und die zugehörigen Abhängigkeiten an einer beliebigen Stelle unter "Programme" oder "(x86),-Programmdateien installiert werden, da alle Windows Store-apps verfügen über Lese- und es standardmäßig Ausführungsberechtigungen.  
  
<a name="Startup"></a>   
### <a name="startup-load"></a>Start laden  
 In der Regel in einer desktop-app die Profiler-Benutzeroberfläche werden aufgefordert, einen Start laden die Profiler-DLL durch die Initialisierung eines Umgebungsblocks, der die erforderlichen Umgebungsvariablen für die CLR Profiling-API enthält (d. h. `COR_PROFILER`, `COR_ENABLE_PROFILING`, und `COR_PROFILER_PATH`), und mit dieser Umgebungsblock wird dann einen neuen Prozess erstellt.  Das gleiche gilt für Windows Store-apps, allerdings sind die Mechanismen verschieden.  
  
 **Führen Sie nicht mit erhöhten rechten**  
 Wenn der Prozess sollte ein versucht beim Erzeugen von Windows Store-app Prozess B, A-Vorgang auf mittlerer Integrität Ebene nicht mit hoher Integritätsstufe ausgeführt werden (die nicht erhöht wird).  Dies bedeutet, dass die Profiler-Benutzeroberfläche mit mittlerer Integritätsstufe ausgeführt werden sollte oder sie müssen einen anderen desktop-Prozess mit mittlerer Integritätsstufe, achten Sie beim Starten von Windows Store-app erzeugen.  
  
 **Auswählen einer Windows Store-App-Profil**  
 Zunächst sollten Sie die Profiler-Benutzer auffordern, die Windows Store-app zu starten.  Bei desktop-apps vielleicht würden Sie den Dialog "Durchsuchen" eine Datei anzeigen, und der Benutzer suchen und wählen Sie eine .exe-Datei würde.  Windows Store-apps werden jedoch andere, und mit einem Dialog "Durchsuchen" keinen Sinn.  Stattdessen ist es besser, die dem Benutzer eine Liste der installierten für diesen Benutzer aus Windows Store-apps anzuzeigen.  
  
 Sie können die [PackageManager-Klasse](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) zum Generieren dieser Liste.  `PackageManager` ist eine Windows-Runtime-Klasse, die in desktop-apps verfügbar ist, und in der Tat *nur* in desktop-apps verfügbar.  
  
 Im folgenden Beispiel der Ode aus einer hypothetischen Profiler-Benutzeroberfläche als eine desktop-app in c# Yses geschrieben der `PackageManager` zum Generieren einer Liste von Windows-apps:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **Angeben der benutzerdefinierten Umgebungsblock**  
 Eine neue COM-Schnittstelle [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), können Sie das Ausführungsverhalten einer Windows Store-App auf einige Formen der Diagnose vereinfachen anpassen.  Einer der Methoden, [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), können Sie einen Umgebungsblock zum Windows Store-app übergeben werden, wenn er gestartet wird, sowie andere nützliche Effekte wie das Deaktivieren von automatischen Prozess anhalten.  Der Umgebungsblock ist wichtig, da es sich handelt, müssen Sie die Umgebungsvariablen angeben (`COR_PROFILER`, `COR_ENABLE_PROFILING`, und `COR_PROFILER_PATH)`) von der CLR verwendet werden, um die Profiler-DLL zu laden.  
  
 Sehen Sie sich den folgenden Codeausschnitt:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 Es gibt eine Reihe von Elementen, die Sie richtig machen müssen:  
  
-   `packageFullName` kann bestimmt werden, während Sie die Pakete durchlaufen und grabbing `package.Id.FullName`.  
  
-   `debuggerCommandLine` ist etwas interessanter.  Um die benutzerdefinierte Umgebungsblock an Windows Store-app übergeben, müssen Sie Ihre eigenen, vereinfachte dummy-Debugger schreiben.  Windows-erzeugt Windows Store-app angehalten, und klicken Sie dann durch starten den Debugger mit einer Befehlszeile wie in diesem Beispiel fügt den Debugger:  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     auf dem `-p 1336` bedeutet, dass Windows Store-app hat die Prozess-ID-1336 und `-tid 1424` bedeutet, dass Thread-ID 1424 ist der Thread, der angehalten wurde.  Dummy-Debugger würde der ThreadID, über die Befehlszeile zu analysieren, diesem Thread fortsetzen und beenden.  
  
     Hier einige Beispiele C++-Code zu diesem Zweck ist (unbedingt fehlerüberprüfung hinzufügen.):  
  
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
  
     Sie müssen dieser dummy-Debugger im Rahmen der Installation-Tool Diagnose bereitstellen, und geben Sie dann den Pfad zu dieser Debugger in der `debuggerCommandLine` Parameter.  
  
 **Starten Windows Store-app**  
 Der Zeitpunkt, an die Windows Store-app zu starten, ist schließlich eingegangen. Wenn Sie sich bereits versucht haben, tun dies selbst, Ihnen möglicherweise aufgefallen, die [CreateProcess](https://msdn.microsoft.com/library/windows/desktop/ms682425\(v=vs.85\).aspx) ist, wie Sie einen Windows Store-app-Prozess nicht erstellen.  Stattdessen müssen Sie mit der [IApplicationActivationManager::ActivateApplication](https://msdn.microsoft.com/library/windows/desktop/Hh706903\(v=vs.85\).aspx) Methode.  Zu diesem Zweck müssen Sie die App-Modell-ID des Windows Store-app zu erhalten, die Sie starten möchten.  Und dies bedeutet, dass Sie müssen ein wenig mehr über das Manifest erforderlich.  
  
 Beim Durchlaufen von Paketen (finden Sie unter "Auswählen einer Windows Store-App zum Profil" in der [Start laden](#Startup) zuvor mithilfe des Abschnitts), benötigen Sie auf den Satz der Anwendungen, die in das aktuelle Paket-Manifest enthaltenen ziehen:  
  
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
  
 Ja, ein Paket kann mehrere Anwendungen haben, und jede Anwendung hat einen eigenen Anwendungsmodell für die Benutzer-ID an.  Daher benötigen Sie die Benutzer bitten, welche Anwendung mit Profil, und ziehen Sie die Anwendung Benutzer Modell-ID aus der betreffenden Anwendung:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
…  
```  
  
 Schließlich können Sie jetzt müssen die Windows Store-app zu starten:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **Denken Sie daran, DisableDebugging aufrufen**  
 Beim Aufruf [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), vorgenommenen eine Zusage, die durch den Aufruf nach selbst bereinigen würde die [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) -Methode, seien Sie sicher, dass führen Wenn die remoteprofilerstellungs-Sitzung ist über.  
  
<a name="Attach"></a>   
### <a name="attach-load"></a>Fügen Sie laden  
 Wenn möchte, dass die Profiler-Benutzeroberfläche die Profiler-DLL für eine Anwendung anfügen, die bereits gestartet wurde, verwendet er [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md).  Das gleiche gilt für Windows Store-apps.  Aber stellen Sie sicher, dass neben den allgemeinen Überlegungen, die weiter oben aufgeführten, die Ziel-Windows Store-app wird nicht angehalten.  
  
 **EnableDebugging**  
 Wie bei Start laden, rufen Sie die [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) Methode.  Ist dies nicht erforderlich für die Übergabe eines Umgebungsblocks, jedoch benötigen Sie einen anderen Features: Deaktivieren von automatischen Prozess anhalten.  Wenn der Profiler-Benutzeroberfläche aufruft, andernfalls [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), die Ziel-Windows Store-app angehalten werden.  Tatsächlich ist dies wahrscheinlich, wenn der Benutzer jetzt mit Ihrem Profiler Benutzeroberfläche interagieren ist und die Windows Store-app nicht aktiv auf einem der Bildschirme des Benutzers ist.  Und wenn die Windows Store-app angehalten wird, sie können auf eine reagieren nicht darauf hinweisen, dass die CLR an sie sendet, die Profiler-DLL angefügt.  
  
 Daher benötigen Sie wie folgt vorzugehen:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 Dies ist der gleiche Aufruf, den Sie für den Start laden Fall machen würden, außer Sie Debugger über die Befehlszeile oder ein Umgebungsblock angeben.  
  
 **DisableDebugging**  
 Wie immer, vergessen Sie nicht, rufen Sie [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) Wenn remoteprofilerstellungs-Sitzung abgeschlossen ist.  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>Innerhalb der Windows Store-app ausgeführt wird  
 Daher hat die Windows Store-app schließlich die Profiler-DLL geladen.  Nun die Profiler-DLL durch die verschiedenen Regeln, die von Windows Store-apps erforderlich wiedergeben unterrichtet werden muss, reduziert, z. B. die APIs zulässig sind und zum Ausführen von mit Berechtigungen.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Halten Sie die Windows Store-app-APIs  
 Wie Sie die Windows-API navigieren, werden Sie feststellen, dass jede API dokumentiert ist, als nicht zutreffend, desktop-apps oder Windows Store-apps.  Z. B. die **Anforderungen** Abschnitt der Dokumentation für die [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) -Funktion zeigt an, dass die Funktion für desktop-apps gelten. Im Gegensatz dazu die [InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx) Funktion ist für desktop-apps und Windows Store-apps verfügbar.  
  
 Wenn Sie die Profiler-DLL zu entwickeln, behandelt, als ob es sich um eine Windows Store-app ist und nur APIs, die als verfügbar für Windows Store-apps dokumentiert sind.  Analysieren Sie die Abhängigkeiten (Sie können z. B. ausführen `link /dump /imports` für die Profiler-DLL zu überwachenden), und suchen Sie dann die docs auszuführen, um festzustellen, welche Ihrer Abhängigkeiten ok sind und die nicht.  In den meisten Fällen können die Verstöße durch Ersetzen sie einfach durch eine neuere Form die API, die als sicher dokumentiert ist korrigiert werden (z. B. ersetzen [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) mit [ InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx)).  
  
 Stellen Sie möglicherweise fest, dass die Profiler-DLL aufruft, einige APIs, die in desktop-apps übernehmen und diese scheinbar noch funktioniert auch, wenn der Profiler-DLL in einer Windows Store-app geladen wird.  Achten Sie darauf, dass sie riskant, verwenden Sie eine beliebige API für die Verwendung mit Windows Store-apps in der Profiler-DLL beim Laden in eine Windows Store-app-Prozess nicht dokumentiert ist:  
  
-   Derartige APIs sind nicht notwendigerweise auch funktionsfähig, wenn im eindeutigen Kontext aufgerufen wird, die in Windows Store-apps ausgeführt.  
  
-   Derartige APIs funktionieren möglicherweise nicht einheitlich, wenn in verschiedenen Prozessen von Windows Store-app aufgerufen.  
  
-   Derartige APIs scheinen problemlos von Windows Store-apps in der aktuellen Version von Windows funktionieren jedoch möglicherweise unterbrechen oder in zukünftigen Versionen von Windows deaktiviert werden.  
  
 Am besten ist, beheben Sie alle Ihre Verstöße und das Risiko zu vermeiden.  
  
 Sie können feststellen, dass absolut nicht ohne eine bestimmte API und nicht werden Ersatz für Windows Store-apps geeignet gefunden kann.  In diesem Fall zumindest:  
  
-   Testen, zu testen, den Lebenshaltungskosten Daylights aus Ihrer Nutzung von dieser API zu testen.  
  
-   Beachten Sie, dass die API plötzlich unterbrochen oder nicht mehr angezeigt, wenn Sie aufgerufen wird möglicherweise von in Windows Store apps in zukünftigen Versionen von Windows.  Dies wird nicht berücksichtigt werden Besorgnis Kompatibilität von Microsoft, und Ihre Nutzung davon unterstützt werden eine Priorität.  
  
<a name="Permissions"></a>   
### <a name="reduced-permissions"></a>Verringerten Berechtigungen  
 Es ist nicht Bestandteil dieses Themas, um alle Möglichkeiten aufzulisten, die Berechtigungen für Windows Store-app von desktop-apps zu unterscheiden.  Aber sicherlich das Verhalten wird jedes Mal, wenn der Profiler-DLL (Wenn in einer Windows Store-app im Vergleich zu einer desktop-app geladen wird) versucht, Zugriff auf die Ressourcen.  Das Dateisystem ist das häufigste Beispiel.  Es gibt jedoch ein paar platziert werden, auf dem Datenträger, die eine bestimmte Windows Store-app zugreifen darf (finden Sie unter [Datei Zugriff und Berechtigungen (Windows-Runtime-apps](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), und die Profiler-DLL ist unter die gleichen Einschränkungen.  Testen Sie den Code sorgfältig durch.  
  
<a name="Interprocess"></a>   
### <a name="inter-process-communication"></a>Prozessübergreifende Kommunikation  
 Wie im Diagramm am Anfang dieses Dokuments dargestellt, müssen die Profiler-DLL (in den Prozessbereich der Windows Store-app geladen) wahrscheinlich die Profiler-Benutzeroberfläche (die in einer separaten desktop-app-Prozessraum ausgeführt wird) über eine eigene benutzerdefinierte prozessübergreifende Kommunikation Kommunikation (IPC)-Kanal.  Der Profiler-Benutzeroberfläche sendet Signale an die Profiler-DLL für ihr Verhalten zu ändern, und die Profiler-DLL sendet Daten aus den analysierten Windows Store-app zurück an die Profiler-Benutzeroberfläche für die Nachbearbeitung und dem Profiler Benutzer angezeigt.  
  
 Die meisten Profiler benötigen, um auf diese Weise zu arbeiten, aber die Optionen für die IPC-Mechanismen sind mehr beschränkt, wenn der Profiler-DLL in einer Windows Store-app geladen werden.  Benannte Pipes sind z. B. nicht Teil von Windows Store-app-SDK, daher nur werden, wenn sie verwendet kann.  
  
 Natürlich bleiben jedoch weiterhin im duplizieren in eingeschränkter Weise.  Ereignisse sind ebenfalls verfügbar.  
  
 **Kommunikation über Dateien**  
 Den größten Teil Ihrer Daten werden über die Dateien wahrscheinlich zwischen der Profiler-DLL und die Profiler-Benutzeroberfläche übergeben.  Der Schlüssel ist, wählen Sie einen Speicherort für die Datei, die der Profiler-DLL (im Rahmen einer Windows Store-app) und die Profiler-Benutzeroberfläche gelesen haben und Schreibzugriff auf.  Z. B. der Pfad des temporären Ordners ist ein Speicherort, den der Profiler-DLL und die Profiler-Benutzeroberfläche zugreifen können, jedoch keine andere Windows Store-app-Paket kann (also alle Informationen, die Sie von anderen Windows Store-app-Paketen protokollieren Abschirmung) zugreifen.  
  
 Der Profiler-Benutzeroberfläche und die Profiler-DLL können diesen Pfad unabhängig ermitteln.  Der Profiler-Benutzeroberfläche beim durchlaufen alle Pakete, die für den aktuellen Benutzer installiert (siehe weiter oben im Beispielcode) Ruft den Zugriff auf die `PackageId` -Klasse, aus der der Pfad des temporären Ordners mit Code wie dieser Ausschnitt abgeleitet werden kann.  (Wie immer wird fehlerüberprüfung aus Gründen der Übersichtlichkeit weggelassen.)  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 In der Zwischenzeit können die Profiler-DLL möglich im Grunde dieselbe Bedeutung, obwohl es kann problemlos erhalten die [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) Klasse, indem die [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) Eigenschaft.  
  
 **Über Ereignisse kommunizieren**  
 Gegebenenfalls einfacher signaling Semantik zwischen Ihrem Profiler-Benutzeroberfläche und die Profiler-DLL können Sie Ereignisse im Windows Store-apps als auch desktop-apps verwenden.  
  
 Über die Profiler-DLL können Sie einfach Aufrufen der [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx) Funktion, um ein benanntes Ereignis mit den gewünschten Namen erstellen soll.  Zum Beispiel:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 Die Profiler-Benutzeroberfläche muss das benannte Ereignis finden Sie unter den Windows Store-app-Namespace zu suchen.  Die Profiler-Benutzeroberfläche konnte aufrufen, z. B. [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx), den Ereignisnamen als angeben  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>` ist die Windows Store-app-AppContainer-SID.  Ein früherer Abschnitt dieses Themas wurde gezeigt, wie die Pakete installiert, die für den aktuellen Benutzer durchlaufen wird.  Aus diesem Beispielcode können Sie die Paket-ID abrufen.  Und aus der Paket-ID, erhalten Sie die `<acSid>` mit Code, der dem folgenden ähnelt:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
<a name="Shutdown"></a>   
### <a name="no-shutdown-notifications"></a>Keine Benachrichtigung zum Herunterfahren  
 Wenn Sie innerhalb einer Windows Store-app ausführen, die Profiler-DLL nicht empfehlenswert entweder [ICorProfilerCallback:: Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) oder sogar [DllMain](https://msdn.microsoft.com/library/windows/desktop/ms682583\(v=vs.85\).aspx) (mit `DLL_PROCESS_DETACH`) aufgerufen werden, um die Profiler-DLL zu benachrichtigen. dass Windows Store-app beendet wird.  In der Tat erwarten, dass sie nie aufgerufen werden.  In der Vergangenheit haben viele Profiler-DLLs verwendet diese Benachrichtigungen als praktische stellen beim Leeren des Caches auf den Datenträger, schließen Sie Dateien, Benachrichtigungen an die Benutzeroberfläche von Profiler usw. gesendet.  Jetzt die Profiler-DLL, muss jedoch ein wenig anders angeordnet werden.  
  
 Der Profiler-DLL sollte darin Protokollierungsinformationen sein.  Aus Gründen der Leistung empfiehlt es sich möglicherweise auf Informationen im Arbeitsspeicher als batch und leert Sie, auf den Datenträger als Batch hinter einem Schwellenwert Wachstum.  Wird jedoch vorausgesetzt, dass alle Informationen, die noch nicht auf den Datenträger geleert verloren gehen kann.  Dies bedeutet, dass den Schwellenwert mit Bedacht auswählen möchten und, dass die Profiler-Benutzeroberfläche muss für den Umgang mit unvollständigen Informationen geschrieben, die von der Profiler-DLL festgeschrieben werden.  
  
<a name="Metadata"></a>   
## <a name="windows-runtime-metadata-files"></a>Windows-Runtime-Metadatendateien  
 Es liegt außerhalb des Bereichs dieses Dokuments im Detail auf welche Windows-Runtime-Metadaten (WinMD) Dateien befinden.    Dieser Abschnitt ist auf der CLR Profiling-API wie reagiert, wenn WinMD-Dateien von Windows Store-app geladen werden, das die Profiler-DLL zu analysieren, ist beschränkt.  
  
<a name="WMDs"></a>   
### <a name="managed-and-non-managed-winmds"></a>Verwaltete und nicht verwaltete WinMDs  
 Wenn ein Entwickler, der von Visual Studio zum Erstellen eines neuen Projekts für Windows Runtime-Komponente verwendet wird, erzeugt ein Build des Projekts eine WinMD-Datei, die die Metadaten (Typ Beschreibungen der Klassen, Schnittstellen, usw.), die vom Entwickler erstellten beschreibt.  Wenn dieses Projekt einer verwalteten Sprache geschrieben in c# oder VB ist, enthält diese gleichen WinMD-Datei auch die Implementierung dieser Typen (d. h., die darin ist die IL, die über den Quellcode des Entwicklers kompiliert).  Solche Dateien werden als verwaltete WinMD-Dateien bezeichnet.  Sie sind interessant, insofern, dass sie Windows-Runtime-Metadaten und die zugrunde liegende Implementierung enthalten.  
  
 Wenn ein Entwickler eine Windows-Runtime-Komponentenprojekt für C++ erstellt wird, im Gegensatz dazu die ein Build des Projekts erzeugt eine WinMD-Datei, die nur Metadaten enthält, und die Implementierung in einer separaten systemeigene DLL kompiliert wird.  Auf ähnliche Weise, enthalten die WinMD-Dateien, die im Windows SDK geliefert nur Metadaten, mit der Implementierung kompiliert aus separaten systemeigene DLLs, die Teil von Windows enthalten sind.  
  
 Die unten aufgeführten Informationen gilt für sowohl verwalteten WinMDs, die Metadaten und den Implementierungscode enthalten, und für nicht verwaltete WinMDs, die nur Metadaten enthalten.  
  
<a name="CLRModules"></a>   
### <a name="winmd-files-look-like-clr-modules"></a>WinMD-Dateien Aussehen von CLR-Module  
 Soweit die CLR wird, werden alle WinMD-Dateien Module an.  CLR Profiling-API weist daher die Profiler-DLL beim Laden der WinMD-Dateien und welche ihrer ModuleIDs, genauso wie andere verwaltete Module verwendet werden.  
  
 Der Profiler-DLL können WinMD-Dateien von anderen Modulen zu unterscheiden, durch Aufrufen der [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) -Methode und Überprüfen der `pdwModuleFlags` output-Parameter für die [COR_PRF_MODULE_WINDOWS_ Common Language RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) Flag.  (Es ist festgelegt Wenn ModuleID ein WinMD darstellt.)  
  
<a name="Reading"></a>   
### <a name="reading-metadata-from-winmds"></a>Lesen von Metadaten aus WinMDs  
 WinMD-Dateien, wie reguläre Module enthalten Metadaten, die über gelesen werden kann die [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).  Allerdings ordnet die CLR beim Lesen, dass die WinMD-Dateien, damit Entwickler, die in verwaltetem Code programmieren, und nutzen die WinMD-Datei eine natürliche Programmierung haben, können Windows-Runtime-Typen in .NET Framework-Typen.  Einige Beispiele für diese Zuordnungen, finden Sie unter [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).  
  
 So die Ansicht der Profiler erhalten, wenn die Metadaten-APIs verwendet: die Windows-Runtime-Rohdatenansicht oder zugeordneten .NET Framework-Sicht?  Antwort: Es liegt an Ihnen.  
  
 Beim Aufrufen der [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) Methode auf ein WinMD auf eine Metadatenschnittstelle, z. B. erhalten [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), Sie können auswählen, legen Sie [OfNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)in der `dwOpenFlags` Parameter für diese Zuordnung zu deaktivieren.  Andernfalls wird standardmäßig die Zuordnung aktiviert werden.  In der Regel wird ein Profiler die Zuordnung aktiviert ist, behalten, damit die Zeichenfolgen, die von den WinMD-Metadaten (z. B. die Namen von Typen) die Profiler-DLL abgerufen vertraut sind und für den Benutzer Profiler natürliche Aussehen.  
  
<a name="Modifying"></a>   
### <a name="modifying-metadata-from-winmds"></a>Ändern von Metadaten aus WinMDs  
 Ändern von Metadaten in WinMDs wird nicht unterstützt.  Beim Aufrufen der [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) Methode für eine WinMD-Datei, und geben Sie [OfWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) in der `dwOpenFlags` Parameter, oder bitten Sie z. B. für eine schreibbare Metadatenschnittstelle [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) schlägt fehl.  Dies ist besonders für IL-Code umschreiben Profiler, ändern Sie die Metadaten, um ihre Instrumentation (z. B. AssemblyRefs oder neue Methoden hinzufügen) unterstützt werden müssen.  Damit Sie überprüfen sollten [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) zunächst (wie im vorherigen Abschnitt erläutert wird) und stellen sicher, dass beschreibbaren Metadatenschnittstellen auf solche Module angefordert werden.  
  
<a name="Resolving"></a>   
### <a name="resolving-assembly-references-with-winmds"></a>Auflösen von Assemblyverweisen mit WinMDs  
 Viele Profiler müssen auflösen Metadatenverweise manuell, um die Instrumentation oder Typ Überprüfung zu unterstützen.  Solche Profiler beachten wie CLR Assemblyverweise, die auf WinMDs, verweisen aufgelöst, da diese Verweise auf eine vollständig andere Weise als standardmäßige Assemblyverweise gelöst werden müssen.  
  
<a name="Profilers"></a>   
## <a name="memory-profilers"></a>Arbeitsspeicher-Profiler  
 Der Garbage Collector und den verwalteten Heap sind nicht grundlegend in einer Windows Store-app und einer desktop-app.  Es gibt jedoch einige feine Unterschiede, denen Entwickler von Profilern berücksichtigen müssen.  
  
<a name="ForceGC"></a>   
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC erstellt einen verwalteten thread  
 Bei der profilerstellung für .NET-Arbeitsspeicher, erstellt die Profiler-DLL in der Regel einen separaten Thread aus dem Aufrufen der [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) Methode.  Dies ist ein bekanntes.  Aber was überraschenden sein könnte, dass das Act Schritte, die eine Garbagecollection innerhalb einer Windows Store-app Ihr Thread in einem verwalteten Thread transformieren möglicherweise ist (z. B. ThreadID-API-Profilerstellung wird für diesen Thread erstellt werden).  
  
 Um die Auswirkungen dieses zu verstehen, ist es wichtig, die Unterschiede zwischen synchronen und asynchronen Aufrufe zu verstehen, wie von der CLR Profiling-API definiert. Beachten Sie, dass dies unterscheidet sich von das Konzept der asynchrone Aufrufe in Windows Store-apps ist.  Finden Sie im Blogbeitrag [wir CORPROF_E_UNSUPPORTED_CALL_SEQUENCE haben](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) für Weitere Informationen.  
  
 Der relevante Punkt ist, dass Aufrufe für Threads, die vom Profiler erstellt immer synchron, berücksichtigt werden, auch wenn diese Aufrufe von außerhalb eine Implementierung eines der Profiler-DLL vorliegen [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Methoden.  Über mindestens, um die Groß-/Kleinschreibung verwendet.  Nun, dass die CLR aufgrund der Aufruf des Profilers Thread in einem verwalteten Thread deaktiviert hat [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), dass Thread des Profilers Thread nicht mehr berücksichtigt wird.  Daher, den die CLR eine strengere Definition, was für diesen Thread als synchrone qualifiziert erzwingt – nämlich, die ein Aufruf vom stammen muss innerhalb eines der Profiler-DLL [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Methoden, wie synchrone zu qualifizieren.  
  
 Was bedeutet dies in der Praxis?  Die meisten [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Methoden sind sicher synchron aufgerufen werden, und treten sofort andernfalls.  Ja, wenn der Profiler-DLL wiederverwendet Ihrer [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) Thread für andere Aufrufe, die in der Regel, die auf der Profiler erstellte Threads (z. B. zum [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), oder [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)), Probleme werden soll.  Auch eine asynchrone sichere-Funktion, z. B. [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) verfügt über spezielle Regeln beim Aufruf in verwalteten Threads. (Finden Sie im Blogbeitrag [Durchlaufen von Stapeln Profiler: Grundlagen und darüber hinaus](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) für Weitere Informationen.)  
  
 Deshalb wird empfohlen, die einen beliebigen Thread die Profiler-DLL erstellt wird, zum Aufrufen [ForceGC-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) zu verwendende *nur* Zweck GCs auslösen, und klicken Sie dann auf die GC-Rückrufe reagiert.  Es sollte nicht in der Profiling-API zum Durchführen anderer Aufgaben wie Stapel sampling oder trennen aufrufen.  
  
<a name="WeakTable"></a>   
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences  
 Beginnend mit .NET Framework 4.5, besteht ein neue GC-Rückruf [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), welche bietet, die der Profiler umfassende Informationen zu *abhängige Handles*. Mit diesen Handles fügen effektiv einen Verweis von einem Quellobjekt in ein Zielobjekt für die Verwaltung der Objektlebensdauer GC.  Abhängige Handles werden keine neuen und Entwickler, die in verwaltetem Code programmieren, erstellen Sie eigene abhängige Handles mithilfe konnten die <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> Klasse auch vor Windows 8 und .NET Framework 4.5.  
  
 Verwalteter XAML-Windows Store-apps stellen jedoch jetzt starke Nutzung von abhängigen Handles.  Insbesondere werden die CLR, die diese unterstützen bei der Verwaltung von Verweis Zyklen zwischen verwalteten Objekten und nicht verwaltete Windows-Runtime-Objekte verwendet.  Dies bedeutet, dass es ist wichtiger als je für Arbeitsspeicher-Profiler dieser abhängigen Ziehpunkte informiert werden, sodass zusammen mit dem Rest des Randes im Heap Diagramm visuell dargestellt werden können.  Der Profiler-DLL zu verwendende [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), und [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) zusammen, um eine vollständige Ansicht des Diagramms Heap zu bilden. .  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Es ist möglich, die CLR Profiling-API verwenden, um verwalteten Code ausgeführt wird, in Windows Store-apps zu analysieren.  Sie können in der Tat nehmen eine vorhandene Profiler, die Sie entwickeln und einige bestimmten Änderungen vornehmen, damit sie Windows Store-apps Ziel verwendet werden kann.   Die Benutzeroberfläche der Profiler sollte die neuen APIs verwenden, für die Aktivierung von Windows Store-app im Debugmodus.  Stellen Sie sicher, dass die Profiler-DLL nur diese APIs, die für Windows Store-apps nutzt.  Der Kommunikationsmechanismus zwischen Ihrem Profiler-DLL und die Benutzeroberfläche von Profiler sollte mit den Windows Store-app-API-Einschränkungen Bedenken und Bewusstsein für die eingeschränkten Berechtigungen an Ort für Windows Store-apps geschrieben werden.  Der Profiler-DLL wie die CLR WinMDs behandelt, bewusst sein, und wie der Garbage Collector-Verhalten in Bezug auf die verwalteten Threads unterscheidet.  
  
<a name="Resources"></a>   
## <a name="resources"></a>Ressourcen  
 **Die Common Language Runtime**  
 -   [CLR Profiling-API-Referenz](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [CLR-Metadaten-API-Referenz](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Die CLR-Interaktion mit der Windows-Runtime**  
 [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
  
 **Windows Store-Apps**  
 -   [Dateizugriff und Berechtigungen (Windows-Runtime-apps](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [Anfordern einer Entwicklerlizenz](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [IPackageDebugSettings-Schnittstelle](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
