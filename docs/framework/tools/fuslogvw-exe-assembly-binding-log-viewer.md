---
title: Fuslogvw.exe (Assembly Binding Log Viewer-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: 2f0018dca6e5add2c5bc531103a4078307a8c8c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129850"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a>Fuslogvw.exe (Assembly Binding Log Viewer-Tool)

In der Assemblybindungs-Protokollanzeige werden Details zu Assemblybindungen angezeigt. Mit diesen Informationen lässt sich leichter diagnostizieren, weshalb zur Laufzeit in .NET Framework keine Assembly gefunden werden kann. Diese Fehler resultieren normalerweise aus einer Assembly, die am falschen Ort bereitgestellt wird, einem systemeigenen Abbild, das nicht mehr gültig ist, oder aus Abweichungen bei Versionsnummern oder Kulturen. Wenn die Common Language Runtime eine Assembly nicht finden kann, wird dies in der Anwendung als <xref:System.TypeLoadException> angezeigt.

> [!IMPORTANT]
> Sie müssen "fuslogvw.exe" mit Administratorrechten ausführen.

Dieses Tool wird automatisch mit Visual Studio installiert. Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7) mit Administratoranmeldeinformationen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

Geben Sie an der Eingabeaufforderung Folgendes ein:

```console
fuslogvw
```

Für jede fehlgeschlagene Assemblybindung wird ein Eintrag angezeigt. Darin sind folgende Daten enthalten: welche Anwendung die Bindung initialisiert hat, für welche Assembly die Bindung bestimmt ist (Name, Version, Kultur und öffentlicher Schlüssel) sowie Datum und Uhrzeit, wann der Fehler aufgetreten ist.

### <a name="to-change-the-log-location-view"></a>So ändern Sie die Anzeige des Protokollspeicherorts

1. Wählen Sie das Optionsfeld **Standard** aus, um Bindungsfehler für alle Anwendungstypen anzuzeigen. Protokolleinträge werden standardmäßig auf dem Datenträger in Verzeichnissen nach Benutzer im WinInet-Cache gespeichert.

2. Wählen Sie das Optionsfeld **Benutzerdefiniert** aus, um Bindungsfehler in dem von Ihnen angegebenen, benutzerdefinierten Verzeichnis anzuzeigen. Sie müssen den benutzerdefinierten Speicherort angeben, in dem die Protokolle von der Runtime gespeichert werden sollen, indem Sie den benutzerdefinierten Protokollspeicherort festlegen. Geben Sie dazu im Dialogfeld **Protokolleinstellungen** einen gültigen Verzeichnisnamen an. Dieses Verzeichnis sollte bis auf die Dateien, die von der Laufzeit generiert werden, leer sein. Wenn es eine ausführbare Datei enthält, die einen zu protokollierenden Fehler erzeugt, wird der Fehler nicht protokolliert, da das Tool versucht, ein Verzeichnis mit dem Namen der ausführbaren Datei zu erstellen. Außerdem schlägt der Versuch fehl, eine ausführbare Datei vom Protokollspeicherort auszuführen.

    > [!NOTE]
    > Anstelle des benutzerdefinierten Bindungspfads wird die Verwendung des standardmäßigen Bindungspfads empfohlen. Der standardmäßige Bindungspfad wird während der Laufzeit im WinInet-Cache gespeichert und daher auch automatisch gelöscht. Wenn Sie einen benutzerdefinierten Bindungspfad festlegen, müssen Sie diesen selbst löschen.

### <a name="to-view-details-about-a-specific-failure"></a>So zeigen Sie Details für einen bestimmten Fehler an

1. Markieren Sie den Anwendungsnamen des gewünschten Eintrags.

2. Klicken Sie auf die Schaltfläche **Protokolldatei anzeigen**. Alternativ können Sie auch auf den markierten Eintrag doppelklicken.

    Für den markierten Bindungsfehler werden folgende Details angezeigt:

    - Der Grund, warum die Bindung fehlgeschlagen ist, z. B. "Datei nicht gefunden" oder "Versionskonflikt".

    - Daten zur Anwendung, welche die Bindung initialisiert hat, z. B. Name und Stammverzeichnis (AppBase) der Anwendung sowie gegebenenfalls eine Beschreibung des privaten Suchpfades.

    - Die Identität der gesuchten Assembly.

    - Gegebenenfalls eine Beschreibung aller angewendeten Versionsrichtlinien (Anwendung, Herausgeber oder Administrator).

    - Angabe, ob die Assembly im [globalen Assemblycache](../app-domains/gac.md) vorhanden ist.

    - Eine Liste aller bei der Untersuchung verwendeten URLs.

Das folgende Beispiel zeigt einen Protokolleintrag mit den Details einer fehlgeschlagenen Assemblybindung.

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="to-delete-a-single-entry-from-the-log"></a>So löschen Sie einen Eintrag aus dem Protokoll

1. Markieren Sie einen Eintrag.

2. Klicken Sie auf die Schaltfläche **Eintrag löschen**.

### <a name="to-delete-all-entries-from-the-log"></a>So löschen Sie alle Einträge aus dem Protokoll

- Klicken Sie auf die Schaltfläche **Alles löschen**.

### <a name="to-refresh-the-user-interface"></a>So aktualisieren Sie die Benutzeroberfläche

- Klicken Sie auf die Schaltfläche **Aktualisieren**. Neue Protokolleinträge werden nicht automatisch in die Anzeige aufgenommen. Sie werden erst angezeigt, wenn Sie auf **Aktualisieren** klicken.

### <a name="to-change-the-log-settings"></a>So ändern Sie die Protokolleinstellungen

- Klicken Sie auf die Schaltfläche **Einstellungen**, um das Dialogfeld **Protokolleinstellungen** zu öffnen.

### <a name="to-view-the-about-dialog"></a>So zeigen Sie das Dialogfeld "Info" an

- Klicken Sie auf die Schaltfläche **Info**.

## <a name="binding-logs-for-native-images"></a>Binden von Protokollen für native Abbilder

Standardmäßig protokolliert "Fuslogvw.exe" normale Assembly-Bindungsanforderungen. Alternativ können Sie Assemblybindungen für native Bilder protokollieren, die mit dem [Native Image Generator (Ngen.exe)](ngen-exe-native-image-generator.md) erstellt wurden.

#### <a name="to-log-assembly-binds-for-native-images"></a>So protokollieren Sie Assemblybindungen für systemeigene Abbildungen

- Wählen Sie in der Gruppe **Kategorien protokollieren** das Optionsfeld **Native Bilder** aus.

Im folgenden Protokoll ist ein Fehler aufgeführt, der von einer Abhängigkeit ausgelöst wurde, die nicht vorhanden war, als das systemeigene Abbild für die Anwendung erstellt wurde. Wenn sich die Abhängigkeiten zur Laufzeit von den Abhängigkeiten beim Ausführen von "Ngen.exe" unterscheiden, ist das Binden an ein systemeigenes Abbild nicht zulässig.

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

Im folgenden Protokoll ist ein Bindungsfehler für das systemeigene Abbild aufgeführt, der aufgetreten, weil sich die Sicherheitseinstellungen auf dem Computer, auf dem die Anwendung ausgeführt wurde, von den Sicherheitseinstellungen unterscheiden, die beim Erstellen des systemeigenen Abbilds festgelegt waren.

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a>Das Dialogfeld "Protokolleinstellungen"

Sie können das Dialogfeld **Protokolleinstellungen** verwenden, um die folgenden Aktionen auszuführen.

#### <a name="to-disable-logging"></a>So deaktivieren Sie die Protokollierung

- Wählen Sie das Optionsfeld **Protokoll deaktiviert** aus.  Beachten Sie, dass diese Option in der Standardeinstellung aktiviert ist.

#### <a name="to-log-assembly-binds-in-exceptions"></a>So protokollieren Sie Assemblybindungen in Ausnahmen

- Wählen Sie das Optionsfeld **In Ausnahmetext protokollieren** aus. Nur die am wenigsten ausführlichen Fusionsprotokollinformationen werden in Ausnahmetext protokolliert. Um die vollständigen Informationen anzuzeigen, müssen Sie eine der anderen Einstellungen verwenden.

  Im wichtigen Hinweis finden Sie Informationen über Assemblys, die als domänenneutrale Assemblys geladen werden.

#### <a name="to-log-assembly-bind-failures"></a>So protokollieren Sie Assemblybindungsfehler

- Wählen Sie das Optionsfeld **Fehler von Bindungen an Datenträger protokollieren** aus.

  Im wichtigen Hinweis finden Sie Informationen über Assemblys, die als domänenneutrale Assemblys geladen werden.

#### <a name="to-log-all-assembly-binds"></a>So protokollieren Sie alle Assemblybindungen

- Wählen Sie das Optionsfeld **Alle Bindungen an Datenträger protokollieren** aus.

  Im wichtigen Hinweis finden Sie Informationen über Assemblys, die als domänenneutrale Assemblys geladen werden.

> [!IMPORTANT]
> Wenn eine Assembly als domänenneutrale Assembly geladen wird, z. B. durch Festlegen der <xref:System.AppDomainSetup.LoaderOptimization%2A>-Eigenschaft auf <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> oder <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, kann das Aktivieren der Protokollierung in einigen Fällen zu Speicherverlust führen. Dies kann der Fall sein, wenn beim Laden eines domänenneutralen Moduls in eine Anwendungsdomäne ein Protokolleintrag erfolgt und später die Anwendungsdomäne entladen wird. Der Protokolleintrag wird möglicherweise erst freigegeben, wenn der Prozess beendet wird. Einige Debugger aktivieren die Protokollierung automatisch.

#### <a name="to-enable-a-custom-log-path"></a>So aktivieren Sie einen benutzerdefinierten Protokollpfad

1. Wählen Sie das Optionsfeld **Benutzerdefinierten Protokollpfad aktivieren** aus.

2. Geben Sie den Pfad in das Textfeld **Benutzerdefinierter Protokollpfad** ein.

> [!NOTE]
> Der [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) verwendet den Internet Explorer-Cache zum Speichern des Bindungsprotokolls. Aufgrund gelegentlicher Beschädigungen des IE-Caches ist es möglich, dass der [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) keine neuen Bindungsprotokolle mehr im Ansichtsfenster anzeigt. In Folge einer solchen Beschädigung kann die .NET-Bindungsinfrastruktur (Fusion) weder in das Bindungsprotokoll schreiben noch daraus lesen. (Dieses Problem tritt nicht auf, wenn Sie einen benutzerdefinierten Protokollpfad verwenden.)  Um die Beschädigung zu beheben und Fusion wieder das Anzeigen von Bindungsprotokollen zu ermöglichen, müssen Sie den IE-Cache löschen. Löschen Sie dazu im Dialogfeld "Internetoptionen" von Internet Explorer die temporären Internetdateien.
>
> Wenn die nicht verwaltete Anwendung die Common Language Runtime durch Implementieren der `IHostAssemblyManager`-Schnittstelle und der `IHostAssemblyStore`-Schnittstelle hostet, können Protokolleinträge nicht im WinInet-Cache gespeichert werden.  Um Protokolleinträge für benutzerdefinierte Hosts anzuzeigen, die diese Schnittstellen implementieren, müssen Sie einen alternativen Protokollpfad angeben.

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a>So aktivieren Sie die Protokollierung für im Windows-App-Container ausgeführte Apps

1. Aktivieren Sie einen benutzerdefinierten Protokollpfad, wie im vorherigen Verfahren beschrieben. Standardmäßig verfügen Apps, die im Windows-App-Container ausgeführt, über eingeschränkten Zugriff auf die Festplatte. Das Verzeichnis, das Sie angeben, erhält Lese-/Schreibzugriff für alle Apps im App-Container.

2. Aktivieren Sie das Kontrollkästchen **Immersive Protokollierung aktivieren**.

    > [!NOTE]
    > Dieses Kontrollkästchen ist nur unter Windows 8 oder höher aktiviert.

## <a name="see-also"></a>Siehe auch

- <xref:System.TypeLoadException>
- [Extras](index.md)
- [Globaler Assemblycache](../app-domains/gac.md)
- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
