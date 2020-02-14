---
title: Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216557"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debugging

MDAs (Managed Debugging Assistants, Assistenten für verwaltetes Debuggen) sind Hilfsmittel für das Debuggen, die mit der CLR (Common Language Runtime) zusammenarbeiten, um Informationen zum Laufzeitzustand bereitzustellen. Die Assistenten generieren Informationsmeldungen über Laufzeitereignisse, die Sie auf keine andere Art abfangen können. Sie können MDAs verwenden, um schwer aufzufindende Anwendungsfehler zu isolieren, die bei Übergängen zwischen verwaltetem und nicht verwaltetem Code auftreten.

Sie können alle MDAs [Aktivieren oder deaktivieren](#enable-and-disable-mdas) , indem Sie der Windows-Registrierung einen Schlüssel hinzufügen oder eine Umgebungsvariable festlegen. Sie können bestimmte MDAs mithilfe von Anwendungskonfigurationseinstellungen aktivieren. In der Konfigurationsdatei der Anwendung können Sie zusätzliche Konfigurationseinstellungen für einige der MDAs festlegen. Da die Konfigurationsdateien beim Laden der Laufzeit analysiert werden, müssen Sie den MDA bereitstellen, bevor die verwaltete Anwendung gestartet wird. Sie können ihn nicht für Anwendungen bereitstellen, die bereits gestartet wurden.

In der folgenden Tabelle sind die MDAs aufgeführt, die mit dem .NET Framework ausgeliefert werden:

|||
|-|-|
|[asynchronousThreadAbort](asynchronousthreadabort-mda.md)|[bindingFailure](bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](dirtycastandcalloninterface-mda.md)|[disconnectedContext](disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](failedqi-mda.md)|[fatalExecutionEngineError](fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](invalidapartmentstatechange-mda.md)|
|[invalidCERCall](invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](invalidgchandlecookie-mda.md)|[invalidIUnknown](invalidiunknown-mda.md)|
|[invalidMemberDeclaration](invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](invalidvariant-mda.md)|[jitCompilationStart](jitcompilationstart-mda.md)|
|[loaderLock](loaderlock-mda.md)|[loadFromContext](loadfromcontext-mda.md)|
|[marshalCleanupError](marshalcleanuperror-mda.md)|[marshaling](marshaling-mda.md)|
|[memberInfoCacheCreation](memberinfocachecreation-mda.md)|[moduloObjectHashcode](moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](noncomvisiblebaseclass-mda.md)|[notMarshalable](notmarshalable-mda.md)|
|[openGenericCERCall](opengenericcercall-mda.md)|[overlappedFreeError](overlappedfreeerror-mda.md)|
|[pInvokeLog](pinvokelog-mda.md)|[pInvokeStackImbalance](pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](raceonrcwcleanup-mda.md)|[reentrancy](reentrancy-mda.md)|
|[releaseHandleFailed](releasehandlefailed-mda.md)|[reportAvOnComRelease](reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](streamwriterbuffereddatalost-mda.md)|[virtualCERCall](virtualcercall-mda.md)|

Standardmäßig aktiviert .NET Framework eine Teilmenge von MDAs für alle verwalteten Debugger. Sie können den Standardsatz in Visual Studio anzeigen, indem Sie im Menü **Debuggen** die Option **Windows** > **Ausnahme Einstellungen** auswählen und dann die Liste der **Assistenten für verwaltetes Debuggen** erweitern.

![Fenster "Ausnahme Einstellungen" in Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Aktivieren und Deaktivieren von MDAs

Sie können MDAs mit einem Registrierungsschlüssel, einer Umgebungsvariablen und Anwendungskonfigurationseinstellungen bereitstellen sowie deren Bereitstellung aufheben. Sie müssen entweder den Registrierungsschlüssel oder die Umgebungsvariable für die Verwendung der Anwendungskonfigurationseinstellungen aktivieren.

> [!TIP]
> Anstatt MDAs zu deaktivieren, können Sie verhindern, dass Visual Studio das MDA-Dialogfeld anzeigt, wenn eine MDA-Benachrichtigung empfangen wird. Wählen Sie hierzu im Menü **Debuggen** die Option **Windows** - > **Ausnahme Einstellungen** aus, erweitern Sie die Liste der **Assistenten für verwaltetes Debuggen** , und aktivieren oder deaktivieren Sie das Kontrollkästchen unter **brechen bei** ausgelöst für den jeweiligen MDA.

### <a name="registry-key"></a>Registrierungsschlüssel

Fügen Sie den **HKEY_LOCAL_MACHINE \Software\Microsoft\\hinzu, um MDAs zu aktivieren. NETFramework\MDA** Unterschlüssel (geben Sie REG_SZ, Wert 1) in der Windows-Registrierung ein. Kopieren Sie das folgende Beispiel in eine Textdatei mit dem Namen " *MDAEnable. reg*". Öffnen Sie den Windows-Registrierungs-Editor (regedit. exe), und wählen Sie im Menü **Datei** die Option **importieren**aus. Wählen Sie die Datei *MDAEnable. reg* aus, um MDAs auf diesem Computer zu aktivieren. Durch Festlegen des unter Schlüssels auf den Zeichen folgen Wert **1** (nicht DWORD-Wert **1**) wird das Lesen der MDA-Einstellungen aus der Datei *ApplicationName. Suffix*. MDA. config ermöglicht. Die MDA-Konfigurationsdatei für Notepad heißt beispielsweise "Notepad. exe. MDA. config".

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

Führt der Computer eine 32-Bit-Anwendung auf einem 64-Bit-System aus, dann sollte der MDA-Schlüssel folgendermaßen festgelegt sein:

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

Weitere Informationen finden Sie unter [anwendungsspezifische Konfigurationseinstellungen](#application-specific-configuration-settings) . Die Registrierungseinstellung kann durch die COMPLUS_MDA-Umgebungsvariable überschrieben werden. Weitere Informationen finden Sie unter [Umgebungs Variable](#environment-variable) .

Legen Sie zum Deaktivieren von MDAs den MDA-Unterschlüssel mit dem Windows-Registrierungs-Editor auf **0** (null) fest.

In der Standardeinstellung werden einige MDAs bereitgestellt, wenn Sie eine Anwendung ausführen, die an einen Debugger angehängt ist. Dies gilt auch, wenn der Registrierungsschlüssel nicht hinzugefügt wurde. Sie können diese Assistenten deaktivieren, indem Sie die Datei *mdadeaktiviert. reg* ausführen, wie weiter oben in diesem Abschnitt beschrieben.

### <a name="environment-variable"></a>Umgebungsvariable

Sie können die Bereitstellung von MDAs auch mithilfe der Umgebungsvariablen COMPLUS_MDA steuern, die den Registrierungsschlüssel überschreibt. Die Zeichenfolge COMPLUS_MDA ist eine durch Semikolons getrennte Liste von MDA-Namen und anderen Steuerzeichenfolgen, in der die Groß- und Kleinschreibung nicht beachtet wird. Bei einem Start unter einem verwalteten oder nicht verwalteten Debugger wird standardmäßig ein Satz MDAs bereitgestellt. Dies wird erzielt, indem die durch Semikolons getrennte Liste der MDAs, die standardmäßig unter Debuggern bereitgestellt werden, dem Wert der Umgebungsvariablen oder des Registrierungsschlüssels vorangestellt wird. Folgende Steuerzeichenfolgen sind verfügbar:

- `0`: Deaktiviert alle MDAs.

- `1`: Liest MDA-Einstellungen aus *ApplicationName*.mda.config.

- `managedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine verwaltete ausführbare Datei unter einem Debugger gestartet wird.

- `unmanagedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine nicht verwaltete ausführbare Datei unter einem Debugger gestartet wird.

Wenn widersprüchliche Einstellungen vorhanden sind, überschreiben die neueren Einstellungen die älteren Einstellungen:

- `COMPLUS_MDA=0`: Deaktiviert alle MDAs einschließlich der MDAs, die implizit unter einem Debugger aktiviert werden.

- `COMPLUS_MDA=gcUnmanagedToManaged` stellt `gcUnmanagedToManaged` zusätzlich zu allen MDAs bereit, die unter einem Debugger implizit aktiviert werden.

- `COMPLUS_MDA=0;gcUnmanagedToManaged` aktiviert `gcUnmanagedToManaged`, aber deaktiviert die MDAs, die andernfalls implizit unter einem Debugger aktiviert werden.

### <a name="application-specific-configuration-settings"></a>Anwendungsspezifische Konfigurationseinstellungen

In der MDA-Konfigurationsdatei für die Anwendung können Sie einige MDAs einzeln bereitstellen und konfigurieren bzw. deren Bereitstellung aufheben. Damit MDAs mithilfe einer Anwendungskonfigurationsdatei konfiguriert werden können, muss entweder der MDA-Registrierungsschlüssel oder die COMPLUS_MDA-Umgebungsvariable festgelegt sein. Die Anwendungskonfigurationsdatei befindet sich i. d. R. im selben Verzeichnis wie die ausführbare Datei (.exe) der Anwendung. Der Dateiname hat das Format *ApplicationName*. MDA. config; beispielsweise "Notepad. exe. MDA. config". In der Anwendungs Konfigurationsdatei aktivierte Assistenten verfügen möglicherweise über Attribute oder Elemente, die speziell zum Steuern des Verhaltens dieses Assistenten entworfen wurden.

Im folgenden Beispiel wird gezeigt, wie Sie das Marshalling aktivieren und [konfigurieren:](marshaling-mda.md)

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

Der `Marshaling`-MDA gibt für jeden Übergang von verwaltetem zu nicht verwaltetem Code in der Anwendung Informationen darüber aus, welcher verwaltete Typ an einen nicht verwalteten Typ gemarshallt wird. Der `Marshaling`-MDA kann auch die Namen der Methoden-und Struktur Felder filtern, die in den untergeordneten **methodFilter** -und **fieldFilter** -Elementen bereitgestellt werden.

Im folgenden Beispiel wird gezeigt, wie mehrere MDAs mithilfe ihrer Standardeinstellungen aktiviert werden:

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> Wenn Sie in einer Konfigurationsdatei mehr als einen Assistenten angeben, müssen Sie diese in alphabetischer Reihenfolge aufführen. Wenn Sie z. B. sowohl den `virtualCERCall`-MDA als auch den `invalidCERCall`-MDA bereitstellen möchten, müssen Sie den `<invalidCERCall />`-Eintrag vor dem `<virtualCERCall />`-Eintrag hinzufügen. Falls die Einträge nicht in alphabetischer Reihenfolge aufgeführt sind, wird eine Meldung mit einer unbehandelten Ausnahme zu einer ungültigen Konfigurationsdatei angezeigt.

## <a name="mda-exceptions"></a>MDA-Ausnahmen

Wenn ein MDA aktiviert ist, ist es auch dann aktiv, wenn der Code nicht unter einem Debugger ausgeführt wird. Wenn ein MDA-Ereignis ausgelöst wird, wenn kein Debugger vorhanden ist, wird die Ereignismeldung in einem Dialogfeld für unbehandelte Ausnahmen angezeigt, obwohl dies keine unbehandelte Ausnahme darstellt. Um das Anzeigen dieses Dialogfelds zu vermeiden, entfernen Sie die Einstellungen zur Aktivierung des MDA, wenn der Code nicht in einer Debugumgebung ausgeführt wird.

Wenn Ihr Code in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio ausgeführt wird, können Sie das Ausnahme Dialogfeld vermeiden, das für bestimmte MDA-Ereignisse angezeigt wird. Wählen Sie hierzu im Menü **Debuggen** die Option **Windows** - > **Ausnahme Einstellungen**aus. Erweitern Sie im Fenster " **Ausnahme Einstellungen** " die Liste der **Assistenten für verwaltetes Debuggen** , und deaktivieren Sie dann das Kontrollkästchen unter **brechen bei** ausgelöst für den jeweiligen MDA. Sie können dieses Dialogfeld auch verwenden, um die Anzeige von MDA-Ausnahme Dialogfeldern zu *aktivieren* .

## <a name="mda-output"></a>MDA-Ausgabe

Die MDA-Ausgabe ähnelt dem folgenden Beispiel, das die Ausgabe der `PInvokeStackImbalance`-MDA anzeigt:

**Ein Ping-Befehl an die PInvoke-Funktion "mdatest! Mdatest. Program:: stdcall"hat den Stapel nicht ausgeglichen. Dies liegt wahrscheinlich daran, dass die verwaltete PInvoke-Signatur nicht mit der nicht verwalteten Ziel Signatur identisch ist. Überprüfen Sie, ob die Aufruf Konvention und die Parameter der PInvoke-Signatur mit der nicht verwalteten Ziel Signatur übereinstimmen.**

## <a name="see-also"></a>Weitere Informationen

- [Debuggen, Ablaufverfolgung und Profilerstellung](index.md)
