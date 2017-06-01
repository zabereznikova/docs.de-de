---
title: "Diagnosing Errors with Managed Debugging Assistants | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHMDA"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "run-time error debugging"
  - "managed code, run-time debugging"
  - "resource debugging"
  - "registry, MDAs"
  - "common language runtime, debugging"
  - "MDAs (managed debugging assistants)"
  - "configuration files [.NET Framework], debugging runtime events"
  - "messages, managed debugging assistants"
  - "application configuration files, managed debugging assistants"
  - "debugging [.NET Framework], managed debugging assistants"
  - "environment variables, MDAs"
  - "access violation debugging [.NET Framework]"
  - "diagnostics, managed debugging assistants"
  - "unmanaged code, run-time debugging"
  - "default debug output stream"
  - "memory, debugging"
  - "app.config files, managed debugging assistants"
  - "managed debugging assistants (MDAs)"
  - "debugging [.NET Framework], run-time errors"
  - "trapping events"
  - "runtime, error debugging"
  - "disabling MDAs"
  - "output, managed debugging assistants"
  - "errors [.NET Framework], managed debugging assistants"
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
caps.latest.revision: 63
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 63
---
# Diagnosing Errors with Managed Debugging Assistants
MDAs \(Managed Debugging Assistants, Assistenten für verwaltetes Debuggen\) sind Hilfsmittel für das Debuggen, die mit der CLR \(Common Language Runtime\) zusammenarbeiten, um Informationen zum Laufzeitzustand bereitzustellen.  Die Assistenten generieren Informationsmeldungen über Laufzeitereignisse, die Sie auf keine andere Art abfangen können.  Sie können MDAs verwenden, um schwer aufzufindende Anwendungsfehler zu isolieren, die bei Übergängen zwischen verwaltetem und nicht verwaltetem Code auftreten.  Alle MDAs können durch Hinzufügen eines Schlüssels zur Windows\-Registrierung oder durch Festlegen einer Umgebungsvariable bereitgestellt bzw. deren Bereitstellung aufgehoben werden.  Sie können bestimmte MDAs mithilfe von Anwendungskonfigurationseinstellungen aktivieren.  In der Konfigurationsdatei der Anwendung können Sie zusätzliche Konfigurationseinstellungen für einige der MDAs festlegen.  Da die Konfigurationsdateien beim Laden der Laufzeit analysiert werden, müssen Sie den MDA bereitstellen, bevor die verwaltete Anwendung gestartet wird.  Sie können ihn nicht für Anwendungen bereitstellen, die bereits gestartet wurden.  
  
> [!NOTE]
>  Wenn ein MDA aktiviert ist, ist er selbst dann aktiv, wenn der Code nicht unter einem Debugger ausgewführt wird.  Wenn ein MDA\-Ereignis ausgelöst wird, wenn kein Debugger vorhanden ist, wird die Ereignismeldung in einem Dialogfeld für unbehandelte Ausnahmen angezeigt, obwohl dies keine unbehandelte Ausnahme darstellt.  Um das Anzeigen dieses Dialogfelds zu vermeiden, entfernen Sie die Einstellungen zur Aktivierung des MDA, wenn der Code nicht in einer Debugumgebung ausgeführt wird.  
  
> [!NOTE]
>  Wenn Ihr Code in der integrierten Entwicklungsumgebung \(IDE\) von Visual Studio ausgeführt wird, können Sie das für bestimmte MDA\-Ereignisse angezeigte Ausnahmedialogfeld umgehen.  Klicken Sie dazu im Menü **Debuggen** auf **Ausnahmen**.  \(Wenn das Menü **Debug** den Befehl **Ausnahmen** nicht enthält, klicken Sie im Menü **Tools** auf **Anpassen**, um ihn hinzuzufügen.\) Erweitern Sie im Dialogfeld **Ausnahmen** die Liste **Assistenten für verwaltetes Debuggen**, und deaktivieren Sie das Kontrollkästchen **Ausgelöst** für den jeweiligen MDA.  Um beispielsweise das Ausnahmedialogfeld für einen [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md) zu umgehen, deaktivieren Sie in der Liste **Assistenten für verwaltetes Debuggen** neben dem entsprechenden Namen das Kontrollkästchen **Ausgelöst**.  Sie können dieses Dialogfeld auch verwenden, um die Anzeige von MDA\-Ausnahmedialogfeldern zu aktivieren.  
  
 In der folgenden Tabelle werden die MDAs im Lieferumfang von .NET Framework aufgeführt.  
  
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
  
 Standardmäßig aktiviert .NET Framework eine Teilmenge von MDAs für alle verwalteten Debugger.  Sie können diese standardmäßige Teilmenge in Visual Studio anzeigen, indem Sie im Menü **Debuggen** auf **Ausnahmen** klicken und die Liste **Assistenten für verwaltetes Debuggen** erweitern.  
  
## Bereitstellen und Aufheben der Bereitstellung von MDAs  
 Sie können MDAs mit einem Registrierungsschlüssel, einer Umgebungsvariablen und Anwendungskonfigurationseinstellungen bereitstellen sowie deren Bereitstellung aufheben.  Sie müssen entweder den Registrierungsschlüssel oder die Umgebungsvariable für die Verwendung der Anwendungskonfigurationseinstellungen aktivieren.  
  
 In Visual Studio ab Version 2005 können Sie, wenn der Hostprozess aktiviert ist, MDAs nicht deaktivieren, die sich in der standardmäßigen Teilmenge befinden, oder MDAs aktivieren, die sich nicht in der standardmäßigen Teilmenge befinden.  Der Hostprozess wird standardmäßig aktiviert, sodass er explizit deaktiviert werden muss.  
  
 Gehen Sie wie folgt vor, um den Hostprozess in Visual Studio zu deaktivieren:  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  
  
2.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
     Das Fenster **Projekt\-Designer** wird angezeigt.  
  
3.  Klicken Sie auf die Registerkarte **Debuggen**.  
  
4.  Deaktivieren Sie im Abschnitt **Debugger aktivieren** das Kontrollkästchen **Visual Studio\-Hostprozess aktivieren**.  
  
 Die Deaktivierung des Hostprozesses kann sich jedoch auf die Leistung auswirken.  Sie können vermeiden, MDAs deaktivieren zu müssen, indem Sie Visual Studio so konfigurieren, dass das MDA\-Dialogfeld nicht angezeigt wird, wenn eine MDA\-Benachrichtigung empfangen wird.  Klicken Sie hierzu im Menü **Debuggen** auf **Ausnahmen**, erweitern Sie die Liste **Assistenten für verwaltetes Debuggen**, und aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Ausgelöst** für den jeweiligen MDA.  
  
### Bereitstellen und Aufheben der Bereitstellung von MDAs mit einem Registrierungsschlüssel  
 Sie können MDAs bereitstellen, indem Sie der Windows\-Registrierung den Unterschlüssel "HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework\\MDA" \(Typ: REG\_SZ, Wert: 1\) hinzufügen.  Kopieren Sie das folgende Beispiel in eine Textdatei mit dem Namen "MDAEnable.reg".  Öffnen Sie den Windows\-Registrierungs\-Editor \(RegEdit.exe\) und wählen Sie **Import** im Menü **Datei**.  Wählen Sie die Datei MDAEnable.reg, um auf diesem Computer MDAs zu aktivieren.  Durch Festlegen des Unterschlüssels auf den Zeichenfolgenwert 1 \(nicht den DWORD\-Wert 1\) wird das Lesen der MDA\-Einstellungen aus der Datei *ApplicationName.suffix*.mda.config ermöglicht.  \(Die MDA\-Konfigurationsdatei für Notepad hätte z. B. den Namen notepad.exe.mda.config\)  
  
```  
Windows Registry Editor Version 5.00  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]  
"MDA"="1"  
  
```  
  
 Führt der Computer eine 32\-Bit\-Anwendung auf einem 64\-Bit\-System aus, dann sollte der MDA\-Schlüssel folgendermaßen festgelegt sein:  
  
```  
Windows Registry Editor Version 5.00   
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]  
"MDA"="1"  
  
```  
  
 Weitere Informationen finden Sie unter [Bereitstellen und Aufheben der Bereitstellung von MDAs mit anwendungsspezifischen Konfigurationseinstellungen](#appConfig).  Die Registrierungseinstellung kann durch die COMPLUS\_MDA\-Umgebungsvariable überschrieben werden.  Weitere Informationen finden Sie unter [Bereitstellen und Aufheben der Bereitstellung von MDAs mit einer Umgebungsvariable](#envVariable).  
  
 Um MDAs zu deaktivieren, legen Sie den MDA\-Unterschlüssel mit dem Windows\-Registrierungs\-Editor auf 0 \(null\) fest.  
  
 In der Standardeinstellung werden einige MDAs bereitgestellt, wenn Sie eine Anwendung ausführen, die an einen Debugger angehängt ist. Dies gilt auch, wenn der Registrierungsschlüssel nicht hinzugefügt wurde.  Hierbei handelt es sich z. B. um [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) und [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md).  Sie können die Bereitstellung dieser Assistenten aufheben, indem Sie die Datei "MDADisable.reg" wie weiter oben in diesem Abschnitt beschrieben ausführen.  
  
<a name="envVariable"></a>   
### Bereitstellen und Aufheben der Bereitstellung von MDAs mit einer Umgebungsvariable  
 Sie können die Bereitstellung von MDAs auch mithilfe der Umgebungsvariablen COMPLUS\_MDA steuern, die den Registrierungsschlüssel überschreibt.  Die Zeichenfolge COMPLUS\_MDA ist eine durch Semikolons getrennte Liste von MDA\-Namen und anderen Steuerzeichenfolgen, in der die Groß\- und Kleinschreibung nicht beachtet wird.  Bei einem Start unter einem verwalteten oder nicht verwalteten Debugger wird standardmäßig ein Satz MDAs bereitgestellt.  Dies wird erzielt, indem die durch Semikolons getrennte Liste der MDAs, die standardmäßig unter Debuggern bereitgestellt werden, dem Wert der Umgebungsvariablen oder des Registrierungsschlüssels vorangestellt wird.  Folgende Steuerzeichenfolgen sind verfügbar:  
  
-   `0`: Deaktiviert alle MDAs.  
  
-   `1` \- Liest MDA\-Einstellungen aus *ApplicationName*.mda.config.  
  
-   `managedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine verwaltete ausführbare Datei unter einem Debugger gestartet wird.  
  
-   `unmanagedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine nicht verwaltete ausführbare Datei unter einem Debugger gestartet wird.  
  
 Wenn widersprüchliche Einstellungen vorhanden sind, überschreiben die neueren Einstellungen die älteren Einstellungen:  
  
-   `COMPLUS_MDA=0`: Deaktiviert alle MDAs einschließlich der MDAs, die implizit unter einem Debugger aktiviert werden.  
  
-   `COMPLUS_MDA=gcUnmanagedToManaged` stellt `gcUnmanagedToManaged` zusätzlich zu allen MDAs bereit, die unter einem Debugger implizit aktiviert werden.  
  
-   `COMPLUS_MDA=0;gcUnmanagedToManaged` aktiviert `gcUnmanagedToManaged`, aber deaktiviert die MDAs, die andernfalls implizit unter einem Debugger aktiviert werden.  
  
<a name="appConfig"></a>   
### Bereitstellen und Aufheben der Bereitstellung von MDAs mit anwendungsspezifischen Konfigurationseinstellungen  
 In der MDA\-Konfigurationsdatei für die Anwendung können Sie einige MDAs einzeln bereitstellen und konfigurieren bzw. deren Bereitstellung aufheben.  Damit MDAs mithilfe einer Anwendungskonfigurationsdatei konfiguriert werden können, muss entweder der MDA\-Registrierungsschlüssel oder die COMPLUS\_MDA\-Umgebungsvariable festgelegt sein.  Die Anwendungskonfigurationsdatei befindet sich i. d. R. im selben Verzeichnis wie die ausführbare Datei \(.exe\) der Anwendung.  Der Dateiname hat das Format *ApplicationName*.mda.config, z. B. "notepad.exe.mda.config".  Assistenten, die über die Anwendungskonfigurationsdatei bereitgestellt werden, können Attribute oder Elemente aufweisen, die speziell für die Steuerung des Verhaltens dieses Assistenten vorgesehen sind.  Im folgenden Beispiel wird veranschaulicht, wie der [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md) bereitgestellt und konfiguriert wird.  
  
```  
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
  
 Der `Marshaling`\-MDA gibt für jeden Übergang von verwaltetem zu nicht verwaltetem Code in der Anwendung Informationen darüber aus, welcher verwaltete Typ an einen nicht verwalteten Typ gemarshallt wird.  Der `Marshaling`\-MDA kann außerdem die Namen der Methoden\- und Strukturfelder filtern, die in den untergeordneten Elementen `<methodFilter>` bzw. `<fieldFilter>` angegeben sind.  
  
 Das folgende Beispiel veranschaulicht, wie Sie mehrere MDAs mithilfe ihrer Standardeinstellungen bereitstellen.  
  
```  
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
>  Wenn Sie in einer Konfigurationsdatei mehr als einen Assistenten angeben, müssen Sie diese in alphabetischer Reihenfolge aufführen.  Wenn Sie z. B. sowohl den `virtualCERCall`\-MDA als auch den `invalidCERCall`\-MDA bereitstellen möchten, müssen Sie den `<invalidCERCall />`\-Eintrag vor dem `<virtualCERCall />`\-Eintrag hinzufügen.  Falls die Einträge nicht in alphabetischer Reihenfolge aufgeführt sind, wird eine Meldung mit einer unbehandelten Ausnahme zu einer ungültigen Konfigurationsdatei angezeigt.  
  
### MDA\-Ausgabe  
 Die Ausgaben der MDAs ähneln dem folgenden Beispiel, in dem die Ausgabe des `pInvokeStackImbalance`\-MDAs veranschaulicht wird.  
  
 `A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack.  This is likely because the managed PInvoke signature does not match the unmanaged target signature.  Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.`  
  
## Siehe auch  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)