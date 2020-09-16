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
ms.openlocfilehash: 8922f057cb59258e2dd002cec4015af518dc255f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553355"
---
# <a name="clr-profilers-and-windows-store-apps"></a>CLR-Profiler und Windows Store-Apps

In diesem Thema wird erläutert, was Sie beim Schreiben von Diagnosetools berücksichtigen müssen, die verwalteten Code analysieren, der in einer Windows Store-App ausgeführt wird. Außerdem enthält es Richtlinien zum Ändern vorhandener Entwicklungs Tools, sodass Sie weiterhin funktionieren, wenn Sie Sie für Windows Store-Apps ausführen. Um diese Informationen zu verstehen, ist es am besten, wenn Sie mit der Common Language Runtime-Profilerstellungs-API vertraut sind. Sie haben diese API bereits in einem Diagnosetool verwendet, das für Windows-Desktop Anwendungen ordnungsgemäß ausgeführt wird, und Sie möchten nun das Tool ändern, um es für Windows Store-Apps korrekt auszuführen.

## <a name="introduction"></a>Einführung

Wenn Sie den Einführungs Absatz überschreiten, sind Sie mit der CLR-Profilerstellungs-API vertraut. Sie haben bereits ein Diagnosetool geschrieben, das gut für verwaltete Desktop Anwendungen geeignet ist. Nun sind Sie neugierig, was Sie tun müssen, damit Ihr Tool mit einer verwalteten Windows Store-App funktioniert. Vielleicht haben Sie bereits versucht, dies zu tun, und haben festgestellt, dass es sich nicht um eine einfache Aufgabe handelt. Tatsächlich gibt es eine Reihe von Überlegungen, die für alle Entwickler von Tools möglicherweise nicht offensichtlich sind. Zum Beispiel:

- Windows Store-Apps werden in einem Kontext mit stark reduzierten Berechtigungen ausgeführt.

- Windows-Metadatendateien haben im Vergleich zu herkömmlichen verwalteten Modulen besondere Merkmale.

- Windows Store-apps haben die Gewohnheit, sich selbst auszusetzen, wenn Interaktivität ausfällt.

- Die prozessübergreifenden Kommunikationsmechanismen können aus verschiedenen Gründen nicht mehr funktionieren.

In diesem Thema werden die Dinge aufgeführt, die Sie kennen müssen, und wie Sie mit ihnen ordnungsgemäß behandelt werden.

Wenn Sie noch nicht mit der CLR-Profilerstellungs-API vertraut sind, überspringen Sie die Ressourcen am Ende dieses Themas, um bessere Einführungs Informationen zu erhalten.

Details zu bestimmten Windows-APIs und deren Verwendung finden Sie auch im Rahmen dieses Themas. Beachten Sie dieses Thema als Ausgangspunkt. Weitere Informationen zu Windows-APIs, auf die hier verwiesen wird, finden Sie in der MSDN-Website.

## <a name="architecture-and-terminology"></a>Architektur und Terminologie

In der Regel hat ein Diagnosetool eine Architektur wie die in der folgenden Abbildung gezeigt. Es verwendet den Begriff "Profiler", aber viele dieser Tools sind über die typische Leistungs-oder Speicher Profilerstellung hinaus in Bereichen wie Code Coverage, Mock-Objekt-Frameworks, Zeit Reise-Debuggen, Anwendungsüberwachung usw. verfügbar. Der Einfachheit halber wird in diesem Thema weiterhin auf all diese Tools als Profiler verwiesen.

In diesem Thema wird die folgende Terminologie verwendet:

**Anwendung**

Dies ist die Anwendung, die der Profiler analysiert. In der Regel verwendet der Entwickler dieser Anwendung jetzt den Profiler, um Probleme mit der Anwendung zu diagnostizieren. Diese Anwendung wäre traditionell eine Windows-Desktop Anwendung, aber in diesem Thema werden Windows Store-Apps untersucht.

**Profiler-DLL**

Dies ist die Komponente, die in den Prozessbereich der analysierten Anwendung geladen wird. Diese Komponente wird auch als Profiler "Agent" bezeichnet und implementiert die [ICorProfilerCallback](icorprofilercallback-interface.md)-Schnitt[Stelle ICorProfilerCallback Interface](icorprofilercallback-interface.md)(2, 3, usw.) und nutzt die [ICorProfilerInfo](icorprofilerinfo-interface.md)-Schnittstellen (2, 3 usw.), um Daten über die analysierte Anwendung zu sammeln und möglicherweise Aspekte des Verhaltens der Anwendung zu ändern.

**Profiler-Benutzeroberfläche**

Dabei handelt es sich um eine Desktop Anwendung, mit der der Profiler-Benutzer interagiert. Er ist dafür verantwortlich, den Anwendungs Status für den Benutzer anzuzeigen und dem Benutzer die Möglichkeit zu geben, das Verhalten der analysierten Anwendung zu steuern. Diese Komponente wird immer in einem eigenen Prozessbereich ausgeführt, getrennt vom Prozessbereich der Anwendung, für die die Profilerstellung ausgeführt wird. Die Profiler-Benutzeroberfläche kann auch als "Anfügevorgang" fungieren. dabei handelt es sich um den Prozess, der die [iclrprofiling:: attachprofiler](iclrprofiling-attachprofiler-method.md) -Methode aufruft, damit die analysierte Anwendung die Profiler-DLL in den Fällen lädt, in denen die Profiler-DLL beim Start nicht geladen wurde.

> [!IMPORTANT]
> Die Profiler-Benutzeroberfläche sollte weiterhin eine Windows-Desktop Anwendung sein, auch wenn Sie zur Steuerung und Berichterstellung in einer Windows Store-App verwendet wird. Es ist nicht zu erwarten, dass Sie Ihr Diagnosetool im Windows Store Verpacken und versenden können. Das Tool muss Aufgaben ausführen, die von Windows Store-Apps nicht möglich sind, und viele dieser Dinge befinden sich in der Profiler-Benutzeroberfläche.

In diesem Dokument geht der Beispielcode von folgendem Beispiel aus:

- Die Profiler-dll ist in C++ geschrieben, da Sie gemäß den Anforderungen der CLR-Profilerstellungs-API eine native dll sein muss.

- Ihre Profiler-Benutzeroberfläche ist in c# geschrieben. Dies ist nicht erforderlich, aber weil es keine Anforderungen an die Sprache für den Prozess ihrer Profiler-Benutzeroberfläche gibt, sollten Sie eine Sprache auswählen, die kurz und einfach ist?

### <a name="windows-rt-devices"></a>Windows RT-Geräte

Windows RT-Geräte sind recht gesperrt. Profiler von Drittanbietern können einfach nicht auf solchen Geräten geladen werden. Dieses Dokument konzentriert sich auf Windows 8-PCs.

## <a name="consuming-windows-runtime-apis"></a>Nutzen von Windows-Runtime-APIs

In einer Reihe von Szenarios, die in den folgenden Abschnitten erläutert werden, muss ihre Profiler UI Desktop-Anwendung einige neue Windows-Runtime-APIs nutzen. Sie sollten sich mit der Dokumentation vertraut machen, um zu verstehen, welche Windows-Runtime APIs von Desktop Anwendungen verwendet werden können und ob Ihr Verhalten bei der Aufruf von Desktop Anwendungen und Windows Store-Apps unterschiedlich ist.

Wenn die Profiler-Benutzeroberfläche in verwaltetem Code geschrieben ist, müssen Sie einige Schritte ausführen, um die Nutzung dieser Windows-Runtime APIs zu erleichtern. Weitere Informationen finden Sie im Artikel [verwaltete Desktop-Apps und Windows-Runtime](/previous-versions/windows/apps/jj856306(v=win.10)) .

## <a name="loading-the-profiler-dll"></a>Laden der Profiler-DLL

In diesem Abschnitt wird beschrieben, wie die Benutzeroberfläche Ihres Profilers bewirkt, dass die Windows Store-App ihre Profiler-DLL lädt. Der in diesem Abschnitt beschriebene Code gehört zu ihrer UI-Desktop-App für Profiler und umfasst daher die Verwendung von Windows-APIs, die für Desktop-Apps sicher sind, aber nicht unbedingt für Windows Store-Apps sicher sind.

Die Profiler-Benutzeroberfläche kann dazu führen, dass die Profiler-DLL auf zwei Arten in den Prozessbereich der Anwendung geladen wird:

- Beim Anwendungsstart, wie von Umgebungsvariablen gesteuert.

- Durch den Aufruf der [iclrprofiling:: attachprofiler](iclrprofiling-attachprofiler-method.md) -Methode an die Anwendung, nachdem der Startvorgang durchgeführt wurde.

Einer ihrer ersten Hindernisse ist das Starten von Start-und Anfüge Ladevorgang ihrer Profiler-DLL, damit Sie ordnungsgemäß mit Windows Store-Apps funktioniert. Beide Arten von laden haben einige besondere Überlegungen gemeinsam, also beginnen wir mit Ihnen.

### <a name="common-considerations-for-startup-and-attach-loads"></a>Allgemeine Überlegungen zum Starten und Anfügen von Ladevorgängen

**Signieren der Profiler-DLL**

Wenn Windows versucht, die Profiler-DLL zu laden, wird überprüft, ob die Profiler-DLL ordnungsgemäß signiert ist. Andernfalls schlägt der Ladevorgang standardmäßig fehl. Hierfür gibt es zwei Möglichkeiten:

- Stellen Sie sicher, dass die Profiler-DLL signiert ist.

- Teilen Sie dem Benutzer mit, dass vor der Verwendung des Tools eine Entwicklerlizenz auf dem Windows 8-Computer installiert werden muss. Dies kann automatisch über Visual Studio oder manuell über eine Eingabeaufforderung erfolgen. Weitere Informationen finden Sie unter [erwerben einer Entwicklerlizenz](/previous-versions/windows/apps/hh974578(v=win.10)).

**Dateisystem Berechtigungen**

Die Windows Store-App muss über die Berechtigung zum Laden und Ausführen ihrer Profiler-DLL von dem Speicherort im Dateisystem verfügen, in dem Sie sich standardmäßig in der Größe befindet. die Windows Store-App verfügt nicht über die entsprechende Berechtigung für die meisten Verzeichnisse, und jeder fehlgeschlagene Versuch, ihre Profiler-DLL zu laden, erzeugt einen Eintrag im Windows-Anwendungs Ereignisprotokoll :

```output
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].
```

Im allgemeinen dürfen Windows Store-Apps nur auf eine begrenzte Anzahl von Speicherorten auf dem Datenträger zugreifen. Jede Windows Store-App kann auf Ihre eigenen Anwendungsdatenordner zugreifen sowie auf einige andere Bereiche im Dateisystem, für die allen Windows Store-Apps der Zugriff gewährt wird. Es empfiehlt sich, die Profiler-DLL und ihre Abhängigkeiten an einem beliebigen Ort unter "Programme" oder "Programme (x86)" zu installieren, da alle Windows Store-Apps standardmäßig über die Berechtigungen Lesen und Ausführen verfügen.

### <a name="startup-load"></a>Start Ladevorgang

In der Regel fordert die Profiler-Benutzeroberfläche in einer Desktop-App einen Start Ladevorgang ihrer Profiler-DLL an, indem ein Umgebungsblock initialisiert wird, der die erforderlichen Umgebungsvariablen der CLR-Profilerstellungs-API (d. h.,, `COR_PROFILER` `COR_ENABLE_PROFILING` und `COR_PROFILER_PATH` ) enthält. Anschließend wird ein neuer Prozess mit diesem Umgebungsblock erstellt. Das gleiche gilt für Windows Store-Apps, aber die Mechanismen unterscheiden sich.

**Nicht mit erhöhten Rechten ausführen**

Wenn Prozess a versucht, den Windows Store-App-Prozess B zu erzeugen, muss Prozess a auf mittlerer Integritäts Ebene ausgeführt werden, nicht auf hoher Integritäts Stufe (d. h. nicht mit erhöhten Rechten). Dies bedeutet, dass entweder die Benutzeroberfläche Ihres Profilers auf mittlerer Integritäts Ebene ausgeführt werden muss, oder es muss ein anderer Desktop Prozess auf mittlerer Integritäts Ebene erzeugt werden, um den Start der Windows Store-App zu übernehmen.

**Auswählen einer Windows Store-App für die Profilerstellung**

Zuerst sollten Sie Ihren Profiler-Benutzer auffordern, welche Windows Store-App gestartet werden soll. Bei Desktop-Apps wird möglicherweise ein Dialogfeld zum Durchsuchen von Dateien angezeigt, und der Benutzer würde eine exe-Datei suchen und auswählen. Windows Store-Apps sind jedoch anders, und die Verwendung eines Dialog Felds zum Durchsuchen ist nicht sinnvoll. Stattdessen ist es besser, dem Benutzer eine Liste der Windows Store-Apps anzuzeigen, die für diesen Benutzer installiert wurden.

Sie können die- <xref:Windows.Management.Deployment.PackageManager> Klasse verwenden, um diese Liste zu generieren. `PackageManager` ist eine Windows-Runtime-Klasse, die für Desktop-Apps verfügbar ist und tatsächlich *nur* für Desktop-Apps verfügbar ist.

Das folgende Codebeispiel aus einer hypothetischen Profiler-Benutzeroberfläche, die als Desktop-app in c# geschrieben wurde `PackageManager` , verwendet, um eine Liste von Windows-apps zu generieren:

```csharp
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();
PackageManager packageManager = new PackageManager();
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);
```

**Angeben des benutzerdefinierten Umgebungs Blocks**

Mit der neuen COM-Schnittstelle [ipackagedebugsettings](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings)können Sie das Ausführungs Verhalten einer Windows Store-App anpassen, um Diagnose Arten einfacher zu gestalten. Mit einer der Methoden " [enabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging)" können Sie einen Umgebungsblock an die Windows Store-App übergeben, wenn dieser gestartet wird, sowie weitere nützliche Effekte wie das Deaktivieren der automatischen Prozessunterbrechung. Der Umgebungsblock ist wichtig, da Sie die Umgebungsvariablen (, und) angeben müssen, die `COR_PROFILER` `COR_ENABLE_PROFILING` `COR_PROFILER_PATH)` von der CLR verwendet werden, um die Profiler-DLL zu laden.

Betrachten Sie den folgenden Codeausschnitt:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, debuggerCommandLine,
                                                                 (IntPtr)fixedEnvironmentPzz);
```

Es gibt eine Reihe von Elementen, die Sie richtig machen müssen:

- `packageFullName` kann beim Durchlaufen der Pakete und beim Durchlaufen bestimmt werden `package.Id.FullName` .

- `debuggerCommandLine` ist etwas interessanter. Um den benutzerdefinierten Umgebungsblock an die Windows Store-App zu übergeben, müssen Sie einen eigenen, vereinfachten Dummy-Debugger schreiben. Windows erzeugt die Windows Store-App angehalten und fügt dann Ihren Debugger an, indem Sie den Debugger mit einer Befehlszeile wie in diesem Beispiel starten:

    ```console
    MyDummyDebugger.exe -p 1336 -tid 1424
    ```

     Where `-p 1336` bedeutet, dass die Windows Store-App die Prozess-ID 1336 hat, und `-tid 1424` bedeutet, dass Thread-ID 1424 der angehaltene Thread ist. Der Dummy-Debugger würde den ThreadID von der Befehlszeile aus analysieren, diesen Thread fortsetzen und dann beenden.

     Im folgenden finden Sie ein Beispiel für den C++-Code.

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

     Sie müssen diesen Dummy-Debugger im Rahmen der Installation des Diagnosetools bereitstellen und dann im-Parameter den Pfad zu diesem Debugger angeben `debuggerCommandLine` .

**Starten der Windows Store-App**

Der Moment, in dem die Windows Store-App gestartet wird, ist schließlich angekommen. Wenn Sie schon einmal versucht haben, dies selbst zu tun, haben Sie möglicherweise bemerkt, dass die Erstellung eines Windows Store-App-Prozesses durch "up [Process](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) " nicht möglich ist. Stattdessen müssen Sie die [iapplicationactivationmanager:: activateapplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) -Methode verwenden. Hierzu müssen Sie die App-Benutzer Modell-ID der Windows Store-App, die Sie starten, erhalten. Dies bedeutet, dass Sie das Manifest etwas durchlaufen müssen.

Beim Durchlaufen ihrer Pakete (Weitere Informationen finden Sie im Abschnitt "Auswählen einer Windows Store-App für das Profil" im Abschnitt " [Start Last](#startup-load) "), sollten Sie den Satz der im Manifest des aktuellen Pakets enthaltenen Anwendungen erfassen:

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

Ja, ein Paket kann mehrere Anwendungen haben, und jede Anwendung verfügt über eine eigene App-Benutzer Modell-ID. Sie sollten also den Benutzer bitten, die Profilerstellung für die Anwendung durchzusetzen und die ID des Anwendungs Benutzer Modells von der jeweiligen Anwendung zu erfassen:

```csharp
while (appsEnum.GetHasCurrent() != 0)
{
    IAppxManifestApplication app = appsEnum.GetCurrent();
    string appUserModelId = app.GetAppUserModelId();
    //...
}
```

Schließlich verfügen Sie nun über das, was Sie zum Starten der Windows Store-App benötigen:

```csharp
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);
```

**Denken Sie daran, disabledebugging aufzurufen.**

Wenn Sie [ipackagedebugsettings:: enabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging)aufgerufen haben, haben Sie eine Zusage erstellt, dass Sie nach selbst eine Bereinigung durchführen, indem Sie die [ipackagedebugsettings::D isabledebug](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) -Methode aufrufen. Achten Sie daher darauf, dass Sie dies tun, wenn die Profil Erstellungs Sitzung übersteigt.

### <a name="attach-load"></a>Ladevorgang anfügen

Wenn die Profiler-Benutzeroberfläche ihre Profiler-DLL an eine Anwendung anfügen möchte, die bereits gestartet wurde, wird [iclrprofile:: attachprofiler](iclrprofiling-attachprofiler-method.md)verwendet. Das gleiche gilt für Windows Store-Apps. Zusätzlich zu den oben aufgeführten allgemeinen Überlegungen müssen Sie sicherstellen, dass die Windows Store-Ziel-APP nicht angehalten wird.

**Enabledebugging**

Wie beim Start Ladevorgang, wird die [ipackagedebugsettings:: enableDebug](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging) -Methode aufgerufen. Sie benötigen Sie nicht für die Übergabe eines Umgebungs Blocks, aber Sie benötigen eines der anderen Features: Deaktivieren der automatischen Prozessunterbrechung. Andernfalls wird die Windows Store-Ziel-App möglicherweise angehalten, wenn die Profiler-Benutzeroberfläche [attachprofiler](iclrprofiling-attachprofiler-method.md)aufruft. Tatsächlich ist dies wahrscheinlich, wenn der Benutzer jetzt mit ihrer Profiler-Benutzeroberfläche interagiert und die Windows Store-App auf keinem der Bildschirme des Benutzers aktiv ist. Wenn die Windows Store-App angehalten wird, kann Sie nicht auf ein Signal reagieren, das von der CLR an die APP gesendet wird, um ihre Profiler-DLL anzufügen.

Daher sollten Sie Folgendes tun:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, null /* debuggerCommandLine */,
                                                                 IntPtr.Zero /* environment */);
```

Dabei handelt es sich um denselben-Befehl, den Sie für den Start Lade Fall ausführen würden, mit dem Unterschied, dass Sie keine Debugger-Befehlszeile oder einen Umgebungsblock angeben.

**Debuggen**

Denken Sie wie immer daran, [ipackagedebugsettings aufzurufen::D isabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) , wenn die Profil Erstellungs Sitzung abgeschlossen ist.

## <a name="running-inside-the-windows-store-app"></a>Ausführung innerhalb der Windows Store-App

Die Windows Store-App hat ihre Profiler-DLL schließlich geladen. Nun muss ihre Profiler-DLL gelehrt werden, wie die verschiedenen für Windows Store-Apps erforderlichen Regeln abgespielt werden, einschließlich der zulässigen APIs und der Art und Weise, wie Sie mit eingeschränkten Berechtigungen ausgeführt werden.

### <a name="stick-to-the-windows-store-app-apis"></a>Halten Sie sich an die APIs für Windows Store-Apps.

Beim Durchsuchen der Windows-API werden Sie feststellen, dass jede API als anwendbar für Desktop-Apps, Windows Store-Apps oder beides dokumentiert ist. Der **Anforderungs** Abschnitt der-Dokumentation für die [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) -Funktion gibt beispielsweise an, dass die-Funktion nur für Desktop-Apps gilt. Im Gegensatz dazu ist die Funktion [initializecriticalsectionex](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) sowohl für Desktop-Apps als auch für Windows Store-Apps verfügbar.

Wenn Sie Ihre Profiler-DLL entwickeln, behandeln Sie Sie so, als ob Sie eine Windows Store-App ist, und verwenden Sie nur APIs, die für Windows Store-Apps als verfügbar dokumentiert sind. Analysieren Sie Ihre Abhängigkeiten (z. b. können Sie `link /dump /imports` die Überprüfung auf der Profiler-DLL ausführen), und Durchsuchen Sie dann die Dokumente, um zu sehen, welche ihrer Abhängigkeiten in Ordnung sind und welche nicht. In den meisten Fällen können Ihre Verstöße korrigiert werden, indem Sie einfach durch eine neuere Form der API ersetzt werden, die als sicher dokumentiert ist (z. b. durch Ersetzen von [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) durch [initializecriticalsectionex](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).

Sie werden feststellen, dass ihre Profiler-DLL einige APIs aufruft, die nur für Desktop-Apps gelten. Sie scheinen aber auch dann zu funktionieren, wenn ihre Profiler-DLL in eine Windows Store-App geladen wird. Beachten Sie, dass es riskant ist, eine API zu verwenden, die nicht für die Verwendung mit Windows Store-Apps in ihrer Profiler-DLL dokumentiert ist, wenn Sie in einen Windows Store-App-Prozess geladen

- Solche APIs können nicht garantiert werden, wenn Sie im eindeutigen Kontext aufgerufen werden, in dem Windows Store-Apps ausgeführt werden.

- Solche APIs funktionieren möglicherweise nicht konsistent, wenn Sie in verschiedenen Windows Store-App-Prozessen aufgerufen werden.

- Diese APIs scheinen in der aktuellen Version von Windows problemlos von Windows Store-Apps zu funktionieren, können aber in zukünftigen Versionen von Windows möglicherweise unterbrechen oder deaktiviert werden.

Die beste Empfehlung ist, alle Verstöße zu beheben und das Risiko zu vermeiden.

Möglicherweise ist es nicht möglich, ohne eine bestimmte API zu verwenden, und Sie können keinen Ersatz finden, der für Windows Store-Apps geeignet ist. In einem solchen Fall gilt mindestens Folgendes:

- Testen, testen und testen Sie die Lebensdauer dieser API.

- Beachten Sie, dass die API in zukünftigen Versionen von Windows plötzlich unterbrechen oder verschwinden kann, wenn Sie in Windows Store-Apps aufgerufen wird. Dies wird von Microsoft nicht als Kompatibilitätsproblem betrachtet, und die Unterstützung ihrer Nutzung ist keine Priorität.

### <a name="reduced-permissions"></a>Reduzierte Berechtigungen

In diesem Thema wird nicht erläutert, wie die Windows Store-App-Berechtigungen von Desktop-Apps abweichen. Das Verhalten unterscheidet sich jedoch jedes Mal, wenn ihre Profiler-DLL (beim Laden in eine Windows Store-App im Vergleich zu einer Desktop-App) versucht, auf Ressourcen zuzugreifen. Das Dateisystem ist das gängigste Beispiel. Eine bestimmte Windows Store-App kann auf eine bestimmte Stelle auf dem Datenträger zugreifen (siehe [Dateizugriff und Berechtigungen (Windows-Runtime-apps](/previous-versions/windows/apps/hh967755(v=win.10))), und die Profiler-DLL unterliegt den gleichen Einschränkungen. Testen Sie Ihren Code gründlich.

### <a name="inter-process-communication"></a>Prozessübergreifende Kommunikation

Wie im Diagramm zu Beginn dieses Artikels gezeigt, muss ihre Profiler-DLL (in den Prozessbereich der Windows Store-App geladen) wahrscheinlich mit ihrer Profiler-Benutzeroberfläche (in einem separaten Prozessbereich der Desktop-app ausgeführt) über ihren eigenen benutzerdefinierten IPC-Kanal (Inter-Process Communication) kommunizieren. Die Profiler-Benutzeroberfläche sendet Signale an die Profiler-DLL, um das Verhalten zu ändern, und die Profiler-DLL sendet Daten von der analysierten Windows Store-App zur Nachbearbeitung und Anzeige an den Profiler-Benutzer zurück an die Profiler-Benutzeroberfläche.

Die meisten Profiler müssen auf diese Weise funktionieren, aber Ihre Optionen für IPC-Mechanismen sind eingeschränkter, wenn ihre Profiler-DLL in eine Windows Store-App geladen wird. Benannte Pipes sind z. b. nicht Teil des Windows Store App SDK, sodass Sie Sie nicht verwenden können.

Allerdings befinden sich die Dateien immer noch in, aber auf eingeschränktere Weise. Ereignisse sind ebenfalls verfügbar.

**Kommunizieren über Dateien**

Die meisten Daten werden wahrscheinlich zwischen der Profiler-DLL und der Profiler-Benutzeroberfläche über Dateien übergeben. Der Schlüssel besteht darin, einen Datei Speicherort auszuwählen, für den sowohl die Profiler-DLL (im Kontext einer Windows Store-App) als auch die Profiler-Benutzeroberfläche Lese-und Schreibzugriff auf haben. Der temporäre Ordner Pfad ist beispielsweise ein Speicherort, auf den sowohl die Profiler-DLL als auch die Profiler-Benutzeroberfläche zugreifen können. es kann jedoch kein anderes Windows Store-App-Paket darauf zugreifen (wodurch alle Informationen geschützt werden, die Sie aus anderen Windows Store-App-Paketen

Sowohl ihre Profiler-Benutzeroberfläche als auch die Profiler-DLL können diesen Pfad unabhängig voneinander bestimmen. Wenn die Benutzeroberfläche des Profilers alle Pakete durchläuft, die für den aktuellen Benutzer installiert sind (siehe Beispielcode weiter oben), wird auf die- `PackageId` Klasse zugegriffen, von der der temporäre Ordner Pfad mit Code abgeleitet werden kann, der mit diesem Code Ausschnitt vergleichbar ist. (Wie immer, wird die Fehlerüberprüfung aus Gründen der Übersichtlichkeit ausgelassen.)

```csharp
// C# code for the Profiler UI.
ApplicationData appData =
    ApplicationDataManager.CreateForPackageFamily(
        packageId.FamilyName);

tempDir = appData.TemporaryFolder.Path;
```

In der Zwischenzeit kann die Profiler-DLL im Grunde dasselbe tun, aber Sie kann <xref:Windows.Storage.ApplicationData> mithilfe der [ApplicationData. Current](xref:Windows.Storage.ApplicationData.Current%2A) -Eigenschaft leichter zur-Klasse gelangen.

**Kommunizieren über Ereignisse**

Wenn Sie eine einfache Signal Semantik zwischen Ihrer Profiler-Benutzeroberfläche und der Profiler-DLL wünschen, können Sie Ereignisse in Windows Store-Apps und Desktop-Apps verwenden.

In der Profiler-DLL können Sie [einfach die Funktion](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) "-Funktion" aufrufen, um ein benanntes Ereignis mit einem beliebigen Namen zu erstellen. Zum Beispiel:

```cpp
// Profiler DLL in Windows Store app (C++).
CreateEventEx(
    NULL,  // Not inherited
    "MyNamedEvent"
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */
    EVENT_ALL_ACCESS);
```

Die Profiler-Benutzeroberfläche muss dann das benannte Ereignis im Namespace der Windows Store-App finden. Beispielsweise könnte ihre Profiler-Benutzeroberfläche " [kreateeventex](/windows/desktop/api/synchapi/nf-synchapi-createeventexa)" aufrufen, wobei der Ereignis Name als

`AppContainerNamedObjects\<acSid>\MyNamedEvent`

`<acSid>` die appcontainer-SID der Windows Store-App. In einem früheren Abschnitt dieses Themas wurde gezeigt, wie die für den aktuellen Benutzer installierten Pakete durchlaufen werden. Aus diesem Beispielcode können Sie die PackageID abrufen. Und aus PackageID können Sie mit Code abrufen, der dem `<acSid>` folgenden ähnelt:

```csharp
IntPtr acPSID;
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);

string acSid;
ConvertSidToStringSid(acPSID, out acSid);

string acDir;
GetAppContainerFolderPath(acSid, out acDir);
```

### <a name="no-shutdown-notifications"></a>Keine Benachrichtigungen zum Herunterfahren

Wenn Sie in einer Windows Store-App ausgeführt werden, sollte sich die Profiler-DLL nicht darauf verlassen, dass entweder [ICorProfilerCallback:: Shutdown](icorprofilercallback-shutdown-method.md) oder sogar [DllMain](/windows/desktop/Dlls/dllmain) (with `DLL_PROCESS_DETACH` ) aufgerufen wird, um ihre Profiler-DLL zu benachrichtigen, dass die Windows Store-App beendet wird. Tatsächlich sollten Sie davon ausgehen, dass Sie nie aufgerufen werden. In der Vergangenheit wurden diese Benachrichtigungen von vielen Profiler-DLLs als bequeme Orte zum leeren von Caches auf den Datenträger, zum Schließen von Dateien, zum Senden von Benachrichtigungen an die Profiler-Benutzeroberfläche usw. verwendet. Jetzt muss ihre Profiler-DLL jedoch etwas anders angeordnet werden.

Ihre Profiler-DLL sollte bei Bedarf Protokollierungs Informationen aufweisen. Aus Leistungsgründen kann es ratsam sein, Informationen in den Arbeitsspeicher zu übertragen und auf den Datenträger zu leeren, wenn die Größe des Batches über einen bestimmten Schwellenwert liegt. Angenommen, alle Informationen, die noch nicht auf den Datenträger geleert wurden, können verloren gehen. Dies bedeutet, dass Sie den Schwellenwert auf die gewünschte Weise auswählen und die Benutzeroberfläche Ihres Profilers für die Bearbeitung unvollständiger Informationen, die von der Profiler-DLL geschrieben wurden, festgelegt werden müssen.

## <a name="windows-runtime-metadata-files"></a>Metadatendateien Windows-Runtime

In diesem Dokument geht es nicht um detaillierte Informationen zu den Windows-Runtime Metadatendateien (winmd). Dieser Abschnitt ist darauf beschränkt, wie die CLR-Profilerstellungs-API reagiert, wenn winmd-Dateien von der Windows Store-App geladen werden, die von ihrer Profiler-DLL analysiert

### <a name="managed-and-non-managed-winmds"></a>Verwaltete und nicht verwaltete winmds

Wenn ein Entwickler Visual Studio zum Erstellen eines neuen Windows-Runtime Komponenten Projekts verwendet, erzeugt ein Build dieses Projekts eine winmd-Datei, die die Metadaten (die Typbeschreibungen von Klassen, Schnittstellen usw.) beschreibt, die vom Entwickler erstellt wurden. Handelt es sich bei dem Projekt um ein in c# geschriebenes verwaltetes Sprachprojekt oder Visual Basic, enthält dieselbe winmd-Datei auch die Implementierung dieser Typen (d. h., Sie enthält alle aus dem Quellcode des Entwicklers kompilierten Il-Dateien). Solche Dateien werden als verwaltete winmd-Dateien bezeichnet. Sie sind interessant, da Sie sowohl Windows-Runtime Metadaten als auch die zugrunde liegende Implementierung enthalten.

Wenn ein Entwickler dagegen ein Windows-Runtime Komponenten Projekt für C++ erstellt, erzeugt ein Build dieses Projekts eine winmd-Datei, die nur Metadaten enthält, und die Implementierung wird in eine separate Native dll kompiliert. Entsprechend enthalten die winmd-Dateien, die im Windows SDK ausgeliefert werden, nur Metadaten, wobei die Implementierung in separate Native DLLs kompiliert wird, die als Teil von Windows ausgeliefert werden.

Die folgenden Informationen gelten für beide verwalteten winmds, die Metadaten und Implementierungen enthalten, sowie für nicht verwaltete winmds, die nur Metadaten enthalten.

### <a name="winmd-files-look-like-clr-modules"></a>Winmd-Dateien sehen wie CLR-Module aus

Soweit die CLR betroffen ist, sind alle winmd-Dateien Module. Die CLR-Profilerstellungs-API weist daher ihre Profiler-DLL an, wenn winmd-Dateien geladen werden und was Ihre ModuleIDs sind, und zwar auf dieselbe Weise wie bei anderen verwalteten Modulen.

Mit der Profiler-DLL können winmd-Dateien von anderen Modulen unterschieden werden, indem die [ICorProfilerInfo3:: GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) -Methode aufgerufen und der `pdwModuleFlags` Output-Parameter für das [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) -Flag überprüft wird. (Sie wird nur dann festgelegt, wenn die ModuleID ein winmd darstellt.)

### <a name="reading-metadata-from-winmds"></a>Lesen von Metadaten aus winmds

Winmd-Dateien enthalten, wie reguläre Module, Metadaten, die über die [Metadaten-APIs](../metadata/index.md)gelesen werden können. Die CLR ordnet jedoch Windows-Runtime Typen .NET Framework Typen zu, wenn Sie winmd-Dateien liest, damit Entwickler, die in verwaltetem Code programmieren und die winmd-Datei nutzen, eine natürlichere Programmierfunktion haben können. Einige Beispiele für diese Zuordnungen finden Sie [unter .NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).

Welche Ansicht erhält der Profiler, wenn er die Metadaten-APIs verwendet: die unformatierte Windows-Runtime Ansicht oder die zugeordnete .NET Framework Ansicht?  Die Antwort: Es liegt an Ihnen.

Wenn Sie die [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) -Methode für ein winmd aufrufen, um eine Metadatenschnittstelle zu erhalten, z. b. [IMetaDataImport](../metadata/imetadataimport-interface.md), können Sie festlegen, dass [ofnotransform](../metadata/coropenflags-enumeration.md) im Parameter festgelegt wird, `dwOpenFlags` um diese Zuordnung zu deaktivieren. Andernfalls wird die Zuordnung standardmäßig aktiviert. In der Regel wird die Zuordnung von einem Profiler aktiviert, sodass die Zeichen folgen, die die Profiler-DLL aus den winmd-Metadaten abruft (z. b. Namen von Typen), dem Profiler-Benutzer vertraut und natürlich angezeigt werden.

### <a name="modifying-metadata-from-winmds"></a>Ändern von Metadaten aus winmds

Das Ändern von Metadaten in winmds wird nicht unterstützt. Wenn Sie die [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) -Methode für eine winmd-Datei aufrufen und [ofWrite](../metadata/coropenflags-enumeration.md) im `dwOpenFlags` Parameter angeben oder eine beschreibbare Metadatenschnittstelle wie [IMetaDataEmit](../metadata/imetadataemit-interface.md)anfordern, schlägt [GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) fehl. Dies ist besonders wichtig für das Il-Umschreiben von Profiler, die Metadaten für die Unterstützung ihrer Instrumentierung ändern müssen (z. b. zum Hinzufügen von AssemblyRefs oder neuer Methoden). Sie sollten also zuerst nach [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) suchen (wie im vorherigen Abschnitt erläutert) und keine beschreibbaren Metadatenschnittstellen für solche Module anfordern.

### <a name="resolving-assembly-references-with-winmds"></a>Auflösen von Assemblyverweisen mit winmds

Viele Profiler müssen Metadatenverweise manuell auflösen, um die Instrumentation oder typuntersuchung zu unterstützen. Solche Profiler müssen wissen, wie die CLR Assemblyverweise auflöst, die auf winmds verweisen, da diese Verweise auf eine völlig andere Weise als Standardassemblyverweise aufgelöst werden.

## <a name="memory-profilers"></a>Arbeitsspeicherprofiler

Die Garbage Collector und der verwaltete Heap unterscheiden sich in einer Windows Store-App und einer Desktop-App nicht grundlegend. Allerdings gibt es einige feine Unterschiede, die Profiler-Autoren kennen müssen.

### <a name="forcegc-creates-a-managed-thread"></a>ForceGC erstellt einen verwalteten Thread.

Bei der Speicher Profilerstellung erstellt die Profiler-DLL in der Regel einen separaten Thread, von dem die Methode der [ForceGC-Methode](icorprofilerinfo-forcegc-method.md) aufgerufen wird. Das ist nichts Neues. Es kann jedoch überraschend sein, dass der Vorgang der Durchführung einer Garbage Collection in einer Windows Store-App den Thread in einen verwalteten Thread umwandelt (z. b. wird eine Profilerstellungs-API für diesen Thread erstellt).

Um die Folgen zu verstehen, ist es wichtig, die Unterschiede zwischen synchronen und asynchronen Aufrufen zu verstehen, wie von der CLR-Profilerstellungs-API definiert. Beachten Sie, dass sich dies vom Konzept der asynchronen Aufrufe in Windows Store-Apps unterscheidet. Weitere Informationen finden Sie im Blog [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) Beitrag.

Der relevante Punkt ist, dass Aufrufe von Threads, die von Ihrem Profiler erstellt wurden, immer als synchron angesehen werden, auch wenn diese Aufrufe von außerhalb einer Implementierung einer der [ICorProfilerCallback](icorprofilercallback-interface.md) -Methoden ihrer Profiler-DLL vorgenommen werden. Dies war zumindest der Fall. Nun, da die CLR den Thread Ihres Profilers aufgrund des Aufrufens der [ForceGC-Methode](icorprofilerinfo-forcegc-method.md)in einen verwalteten Thread verwandelt hat, wird dieser Thread nicht mehr als Thread des Profilers angesehen. Die CLR erzwingt daher eine strengere Definition, was für diesen Thread synchron ist – d.., dass ein-Befehl aus einer der [ICorProfilerCallback](icorprofilercallback-interface.md) -Methoden ihrer Profiler-DLL stammen muss, um als synchron zu qualifizieren.

Was bedeutet dies in der Praxis? Die meisten [ICorProfilerInfo](icorprofilerinfo-interface.md) -Methoden können nur synchron aufgerufen werden. andernfalls tritt ein Fehler auf. Wenn Ihre Profiler-DLL Ihren [ForceGC-Methoden](icorprofilerinfo-forcegc-method.md) Thread für andere Aufrufe wieder verwendet, die in der Regel für von Profiler erstellte Threads (z. b. [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md), [requestrejit](icorprofilerinfo4-requestrejit-method.md)oder [requestrevert](icorprofilerinfo4-requestrevert-method.md)) durchgeführt werden, haben Sie Probleme. Auch eine asynchrone sichere Funktion wie [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) verfügt über spezielle Regeln, wenn Sie von verwalteten Threads aufgerufen wird. (Weitere Informationen finden Sie im Blogbeitrag [Profiler Stack Walking: Basics und Beyond](/archive/blogs/davbr/profiler-stack-walking-basics-and-beyond) .)

Daher empfiehlt es sich, dass jeder Thread, der von der Profiler-DLL zum Aufrufen der [ForceGC-Methode](icorprofilerinfo-forcegc-method.md) erstellt wird, *nur* für das Auslösen von GCS und dann das reagieren auf die GC-Rückrufe verwendet werden soll. Es sollte nicht in die Profilerstellungs-API aufgerufen werden, um andere Aufgaben wie z. b

### <a name="conditionalweaktablereferences"></a>Conditionalweaktablereferences

Beginnend mit dem .NET Framework 4,5 gibt es einen neuen GC-Rückruf, [conditionalweaktableelementreferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md), der dem Profiler ausführlichere Informationen über *abhängige Handles*liefert. Diese Handles fügen effektiv einen Verweis aus einem Quell Objekt zu einem Zielobjekt für die Verwaltung der GC-Lebensdauer hinzu. Abhängige Handles sind nichts neues, und Entwickler, die in verwaltetem Code programmieren, können eigene abhängige Handles erstellen, indem Sie die <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> -Klasse auch vor Windows 8 und der .NET Framework 4,5 verwenden.

Verwaltete XAML-Windows Store-Apps nutzen nun jedoch die abhängigen Handles stark. Insbesondere verwendet die CLR diese, um die Verwaltung von Verweis Zyklen zwischen verwalteten Objekten und nicht verwalteten Windows-Runtime Objekten zu unterstützen. Dies bedeutet, dass es jetzt wichtiger ist, dass Speicher Profiler über diese abhängigen Handles informiert werden, damit Sie zusammen mit den restlichen Rändern im Heap Diagramm visualisiert werden können. Die Profiler-DLL sollte " [RootReferences2](icorprofilercallback2-rootreferences2-method.md)", " [ObjectReferences](icorprofilercallback-objectreferences-method.md)" und " [conditionalweaktableelementreferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) " verwenden, um eine umfassende Ansicht des Heap Diagramms zu bilden.

## <a name="conclusion"></a>Zusammenfassung

Es ist möglich, mit der CLR-Profilerstellungs-API verwalteten Code zu analysieren, der in Windows Store-Apps ausgeführt wird. Tatsächlich können Sie einen vorhandenen Profiler erstellen, den Sie entwickeln, und bestimmte Änderungen vornehmen, sodass er auf Windows Store-Apps abzielen kann. Die Profiler-Benutzeroberfläche sollte die neuen APIs zum Aktivieren der Windows Store-App im Debugmodus verwenden. Stellen Sie sicher, dass die Profiler-DLL nur die APIs verwendet, die für Windows Store-Apps anwendbar sind. Der Kommunikationsmechanismus zwischen Ihrer Profiler-DLL und der Profiler-Benutzeroberfläche sollte mit den Einschränkungen der Windows Store-App-API und mit dem Bewusstsein der eingeschränkten Berechtigungen für Windows Store-Apps geschrieben werden. Die Profiler-DLL sollte wissen, wie die CLR winmds behandelt und wie sich das Verhalten des Garbage Collectors in Bezug auf verwaltete Threads unterscheidet.

## <a name="resources"></a>Ressourcen

**Common Language Runtime**

- [Profilerstellung (Referenz zur nicht verwalteten API)](index.md)

- [Metadaten (Referenz zur nicht verwalteten API)](../metadata/index.md)

**Die CLR-Interaktion mit der Windows-Runtime**

- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)

**Windows Store-Apps**

- [Dateizugriff und-Berechtigungen (Windows-Runtime-apps](/previous-versions/windows/apps/hh967755(v=win.10))

- [Anfordern einer Entwicklerlizenz](/previous-versions/windows/apps/hh974578(v=win.10))

- [Ipackagedebugsettings-Schnittstelle](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings)
