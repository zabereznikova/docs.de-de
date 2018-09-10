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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873168"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen

MDAs (Managed Debugging Assistants, Assistenten für verwaltetes Debuggen) sind Hilfsmittel für das Debuggen, die mit der CLR (Common Language Runtime) zusammenarbeiten, um Informationen zum Laufzeitzustand bereitzustellen. Die Assistenten generieren Informationsmeldungen über Laufzeitereignisse, die Sie auf keine andere Art abfangen können. Sie können MDAs verwenden, um schwer aufzufindende Anwendungsfehler zu isolieren, die bei Übergängen zwischen verwaltetem und nicht verwaltetem Code auftreten.

Sie können [aktivieren oder deaktivieren Sie](#enable-and-disable-mdas) alle MDAs, die durch Hinzufügen eines Schlüssels in der Windows-Registrierung oder durch Festlegen einer Umgebungsvariablen. Sie können bestimmte MDAs mithilfe von Anwendungskonfigurationseinstellungen aktivieren. In der Konfigurationsdatei der Anwendung können Sie zusätzliche Konfigurationseinstellungen für einige der MDAs festlegen. Da die Konfigurationsdateien beim Laden der Laufzeit analysiert werden, müssen Sie den MDA bereitstellen, bevor die verwaltete Anwendung gestartet wird. Sie können ihn nicht für Anwendungen bereitstellen, die bereits gestartet wurden.

Die folgende Tabelle enthält die MDAs im Lieferumfang mit .NET Framework:

|||
|-|-|
|[asynchronousThreadAbort](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[bindingFailure](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[disconnectedContext](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[fatalExecutionEngineError](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|
|[invalidCERCall](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|
|[invalidMemberDeclaration](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|
|[loaderLock](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[loadFromContext](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|
|[marshalCleanupError](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|
|[memberInfoCacheCreation](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[moduloObjectHashcode](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[notMarshalable](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|
|[openGenericCERCall](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|
|[pInvokeLog](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[reentrancy](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|
|[releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[virtualCERCall](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|

Standardmäßig aktiviert .NET Framework eine Teilmenge von MDAs für alle verwalteten Debugger. Sie können den Standardsatz in Visual Studio, durch Auswahl anzeigen **Windows** > **Ausnahmeeinstellungen** auf die **Debuggen** Menü und dann erweitern die **Managed Debugging Assistants** Liste.

![Fenster Ausnahmeeinstellungen in Visual Studio](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Aktivieren und Deaktivieren von MDAs

Sie können MDAs mit einem Registrierungsschlüssel, einer Umgebungsvariablen und Anwendungskonfigurationseinstellungen bereitstellen sowie deren Bereitstellung aufheben. Sie müssen entweder den Registrierungsschlüssel oder die Umgebungsvariable für die Verwendung der Anwendungskonfigurationseinstellungen aktivieren.

> [!TIP]
> Anstelle der Bereitstellung von MDAs, können Sie verhindern, dass Visual Studio die MDA-Dialogfeld angezeigt, wenn eine MDA-Benachrichtigung empfangen wird. Zu diesem Zweck wählen **Windows** > **Ausnahmeeinstellungen** auf die **Debuggen** Menü erweitern Sie die **Managed Debugging Assistants**aufzulisten, und aktivieren bzw. deaktivieren Sie die **unterbrechen Wenn ausgelöst** das Kontrollkästchen für den jeweiligen MDA.

### <a name="registry-key"></a>-Registrierungsschlüssel

Um MDAs zu aktivieren, fügen die **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\MDA** Unterschlüssel (Typ: REG_SZ, Wert 1) in der Windows-Registrierung. Kopieren Sie im folgenden Beispiel wird in eine Textdatei namens *"MDAEnable.reg"*. Öffnen Sie den Windows-Registrierungs-Editor (RegEdit.exe), und von der **Datei** Menü **Import**. Wählen Sie die *"MDAEnable.reg"* Datei, die auf diesem Computer MDAs zu aktivieren. Durch Festlegen des Unterschlüssels Zeichenfolgenwert eines **1** (nicht DWORD-Wert, der **1**) ermöglicht das Lesen der MDA-Einstellungen aus der *ApplicationName.suffix*. mda.config-Datei. Der MDA-Konfigurationsdatei für Notepad würde z. B. den Namen notepad.exe.mda.config sein.

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

Finden Sie unter [anwendungsspezifischen Konfigurationseinstellungen](#application-specific-configuration-settings) für Weitere Informationen. Die Registrierungseinstellung kann durch die COMPLUS_MDA-Umgebungsvariable überschrieben werden. Finden Sie unter [Umgebungsvariable](#environment-variable) für Weitere Informationen.

Um MDAs zu deaktivieren, legen Sie den MDA-Unterschlüssel auf **0** (null), mit der Windows-Registrierungs-Editor.

In der Standardeinstellung werden einige MDAs bereitgestellt, wenn Sie eine Anwendung ausführen, die an einen Debugger angehängt ist. Dies gilt auch, wenn der Registrierungsschlüssel nicht hinzugefügt wurde. Sie können dieser Assistenten deaktivieren, indem Sie Ausführung der *"MDADisable.reg"* wie weiter oben in diesem Abschnitt beschrieben.

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

### <a name="application-specific-configuration-settings"></a>Anwendungsspezifische Einstellungen

In der MDA-Konfigurationsdatei für die Anwendung können Sie einige MDAs einzeln bereitstellen und konfigurieren bzw. deren Bereitstellung aufheben. Damit MDAs mithilfe einer Anwendungskonfigurationsdatei konfiguriert werden können, muss entweder der MDA-Registrierungsschlüssel oder die COMPLUS_MDA-Umgebungsvariable festgelegt sein. Die Anwendungskonfigurationsdatei befindet sich i. d. R. im selben Verzeichnis wie die ausführbare Datei (.exe) der Anwendung. Der Dateiname hat das Format *ApplicationName*.mda.config, z.B. „notepad.exe.mda.config“. Assistenten, die über die Anwendungskonfigurationsdatei bereitgestellt werden, können Attribute oder Elemente aufweisen, die speziell für die Steuerung des Verhaltens dieses Assistenten vorgesehen sind.

Das folgende Beispiel zeigt, wie Sie zum Aktivieren und Konfigurieren der [Marshalling](../../../docs/framework/debug-trace-profile/marshaling-mda.md):

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

Der `Marshaling`-MDA gibt für jeden Übergang von verwaltetem zu nicht verwaltetem Code in der Anwendung Informationen darüber aus, welcher verwaltete Typ an einen nicht verwalteten Typ gemarshallt wird. Die `Marshaling` MDA kann auch filtern, die Namen der Methoden- und Strukturfelder im angegebenen die **MethodFilter** und **FieldFilter** untergeordnete Elemente, bzw.

Das folgende Beispiel zeigt, wie Sie mehrere MDAs mithilfe ihrer Standardeinstellungen:

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

Wenn ein MDA aktiviert ist, ist er aktiv selbst wenn Ihr Code nicht unter einem Debugger ausgeführt wird. Wenn ein MDA-Ereignis ausgelöst wird, wenn kein Debugger vorhanden ist, wird die Ereignismeldung in einem Dialogfeld für unbehandelte Ausnahmen angezeigt, obwohl dies keine unbehandelte Ausnahme darstellt. Um das Anzeigen dieses Dialogfelds zu vermeiden, entfernen Sie die Einstellungen zur Aktivierung des MDA, wenn der Code nicht in einer Debugumgebung ausgeführt wird.

Wenn Ihr Code in der integrierten Entwicklungsumgebung (IDE) von Visual Studio ausgeführt wird, können Sie das Ausnahmedialogfeld vermeiden, das für bestimmte MDA-Ereignisse angezeigt. In diesem Fall tun, auf die **Debuggen** Menü wählen **Windows** > **Ausnahmeeinstellungen**. In der **Ausnahmeeinstellungen** Fenster, erweitern Sie die **Managed Debugging Assistants** aus, und deaktivieren Sie dann die **unterbrechen Wenn ausgelöst** das Kontrollkästchen für den jeweiligen MDA. Sie können dieses Dialogfeld auch verwenden *aktivieren* die Anzeige von MDA-ausnahmedialogfeldern.

## <a name="mda-output"></a>MDA-Ausgabe

MDA sieht in etwa wie im folgenden Beispiel, in dem die Ausgabe zeigt die `PInvokeStackImbalance` MDA:

**Ein Aufruf von PInvoke-Funktion "MDATest! MDATest.Program::StdCall' hat einen nicht ausgeglichenen Stapel. Dies ist wahrscheinlich, weil die verwaltete PInvoke-Signatur nicht die Signatur nicht verwaltetes Ziel übereinstimmt. Überprüfen Sie, dass die Aufrufkonvention und die Parameter von PInvoke-Signatur die nicht verwalteten Ziel-Signatur entsprechen.**

## <a name="see-also"></a>Siehe auch

- [Debuggen, Ablaufverfolgung und Profilerstellung](../../../docs/framework/debug-trace-profile/index.md)
