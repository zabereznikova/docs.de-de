---
title: Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen
description: Diagnostizieren von Fehlern in .net mit Assistenten für verwaltetes Debuggen. MDAs sind Debugginghilfen, die in Verbindung mit der CLR zum Bereitstellen von Lauf Zeit Zustandsinformationen arbeiten
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
ms.openlocfilehash: ac6fdc09fb057cc55659ce076d37ab96fe2354d1
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416095"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="2e7a2-104">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debugging</span><span class="sxs-lookup"><span data-stu-id="2e7a2-104">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="2e7a2-105">MDAs (Managed Debugging Assistants, Assistenten für verwaltetes Debuggen) sind Hilfsmittel für das Debuggen, die mit der CLR (Common Language Runtime) zusammenarbeiten, um Informationen zum Laufzeitzustand bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-105">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="2e7a2-106">Die Assistenten generieren Informationsmeldungen über Laufzeitereignisse, die Sie auf keine andere Art abfangen können.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-106">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="2e7a2-107">Sie können MDAs verwenden, um schwer aufzufindende Anwendungsfehler zu isolieren, die bei Übergängen zwischen verwaltetem und nicht verwaltetem Code auftreten.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-107">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="2e7a2-108">Sie können alle MDAs [Aktivieren oder deaktivieren](#enable-and-disable-mdas) , indem Sie der Windows-Registrierung einen Schlüssel hinzufügen oder eine Umgebungsvariable festlegen.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-108">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="2e7a2-109">Sie können bestimmte MDAs mithilfe von Anwendungskonfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-109">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="2e7a2-110">In der Konfigurationsdatei der Anwendung können Sie zusätzliche Konfigurationseinstellungen für einige der MDAs festlegen.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-110">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="2e7a2-111">Da die Konfigurationsdateien beim Laden der Laufzeit analysiert werden, müssen Sie den MDA bereitstellen, bevor die verwaltete Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-111">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="2e7a2-112">Sie können ihn nicht für Anwendungen bereitstellen, die bereits gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-112">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="2e7a2-113">In der folgenden Tabelle sind die MDAs aufgeführt, die mit dem .NET Framework ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="2e7a2-113">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="2e7a2-114">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="2e7a2-114">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="2e7a2-115">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="2e7a2-115">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="2e7a2-116">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="2e7a2-116">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="2e7a2-117">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="2e7a2-117">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="2e7a2-118">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="2e7a2-118">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="2e7a2-119">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="2e7a2-119">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="2e7a2-120">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="2e7a2-120">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="2e7a2-121">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="2e7a2-121">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="2e7a2-122">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="2e7a2-122">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="2e7a2-123">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="2e7a2-123">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="2e7a2-124">failedQI</span><span class="sxs-lookup"><span data-stu-id="2e7a2-124">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="2e7a2-125">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="2e7a2-125">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="2e7a2-126">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="2e7a2-126">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="2e7a2-127">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="2e7a2-127">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="2e7a2-128">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="2e7a2-128">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="2e7a2-129">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="2e7a2-129">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="2e7a2-130">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="2e7a2-130">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="2e7a2-131">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="2e7a2-131">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="2e7a2-132">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="2e7a2-132">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="2e7a2-133">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="2e7a2-133">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="2e7a2-134">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="2e7a2-134">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="2e7a2-135">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="2e7a2-135">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="2e7a2-136">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="2e7a2-136">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="2e7a2-137">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="2e7a2-137">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="2e7a2-138">loaderLock</span><span class="sxs-lookup"><span data-stu-id="2e7a2-138">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="2e7a2-139">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="2e7a2-139">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="2e7a2-140">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="2e7a2-140">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="2e7a2-141">marshaling</span><span class="sxs-lookup"><span data-stu-id="2e7a2-141">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="2e7a2-142">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="2e7a2-142">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="2e7a2-143">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="2e7a2-143">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="2e7a2-144">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="2e7a2-144">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="2e7a2-145">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="2e7a2-145">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="2e7a2-146">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="2e7a2-146">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="2e7a2-147">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="2e7a2-147">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="2e7a2-148">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="2e7a2-148">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="2e7a2-149">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="2e7a2-149">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="2e7a2-150">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="2e7a2-150">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="2e7a2-151">Eintritts Invarianz</span><span class="sxs-lookup"><span data-stu-id="2e7a2-151">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="2e7a2-152">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="2e7a2-152">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="2e7a2-153">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="2e7a2-153">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="2e7a2-154">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="2e7a2-154">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="2e7a2-155">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="2e7a2-155">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="2e7a2-156">Standardmäßig aktiviert .NET Framework eine Teilmenge von MDAs für alle verwalteten Debugger.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-156">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="2e7a2-157">Sie können den Standardsatz in Visual Studio anzeigen, indem **Windows**Sie im  >  Menü **Debuggen** die Option Windows-**Ausnahme Einstellungen** auswählen und dann die Liste **Assistenten für verwaltetes Debuggen** erweitern.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-157">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Fenster "Ausnahme Einstellungen" in Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="2e7a2-159">Aktivieren und Deaktivieren von MDAs</span><span class="sxs-lookup"><span data-stu-id="2e7a2-159">Enable and Disable MDAs</span></span>

<span data-ttu-id="2e7a2-160">Sie können MDAs mit einem Registrierungsschlüssel, einer Umgebungsvariablen und Anwendungskonfigurationseinstellungen bereitstellen sowie deren Bereitstellung aufheben.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-160">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="2e7a2-161">Sie müssen entweder den Registrierungsschlüssel oder die Umgebungsvariable für die Verwendung der Anwendungskonfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-161">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="2e7a2-162">Anstatt MDAs zu deaktivieren, können Sie verhindern, dass Visual Studio das MDA-Dialogfeld anzeigt, wenn eine MDA-Benachrichtigung empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-162">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="2e7a2-163">Wählen Sie hierzu **Windows**  >  im Menü **Debuggen** die Option Windows-**Ausnahme Einstellungen** aus, erweitern Sie die Liste **Assistenten für verwaltetes Debuggen** , und aktivieren oder deaktivieren Sie das Kontrollkästchen **bei auslösen Abbrechen** für den jeweiligen MDA.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-163">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="2e7a2-164">Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="2e7a2-164">Registry Key</span></span>

<span data-ttu-id="2e7a2-165">Fügen Sie zum Aktivieren von MDAs **HKEY_LOCAL_MACHINE \Software\Microsoft hinzu \\ . NETFramework\MDA** Unterschlüssel (geben Sie REG_SZ, Wert 1) in der Windows-Registrierung ein.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-165">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="2e7a2-166">Kopieren Sie das folgende Beispiel in eine Textdatei mit dem Namen " *MDAEnable. reg*". Öffnen Sie den Windows-Registrierungs-Editor (RegEdit.exe), und wählen Sie im Menü **Datei** die Option **importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-166">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="2e7a2-167">Wählen Sie die Datei *MDAEnable. reg* aus, um MDAs auf diesem Computer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-167">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="2e7a2-168">Beim Festlegen des unter Schlüssels auf den Zeichen folgen Wert **1** (nicht auf den DWORD-Wert **1**) wird das Lesen der MDA-Einstellungen aus der Datei " *ApplicationName. Suffix*.mda.config" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-168">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="2e7a2-169">Die MDA-Konfigurationsdatei für Notepad heißt beispielsweise notepad.exe.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-169">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="2e7a2-170">Führt der Computer eine 32-Bit-Anwendung auf einem 64-Bit-System aus, dann sollte der MDA-Schlüssel folgendermaßen festgelegt sein:</span><span class="sxs-lookup"><span data-stu-id="2e7a2-170">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="2e7a2-171">Weitere Informationen finden Sie unter [anwendungsspezifische Konfigurationseinstellungen](#application-specific-configuration-settings) .</span><span class="sxs-lookup"><span data-stu-id="2e7a2-171">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="2e7a2-172">Die Registrierungseinstellung kann durch die COMPLUS_MDA-Umgebungsvariable überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-172">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="2e7a2-173">Weitere Informationen finden Sie unter [Umgebungs Variable](#environment-variable) .</span><span class="sxs-lookup"><span data-stu-id="2e7a2-173">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="2e7a2-174">Legen Sie zum Deaktivieren von MDAs den MDA-Unterschlüssel mit dem Windows-Registrierungs-Editor auf **0** (null) fest.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-174">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="2e7a2-175">In der Standardeinstellung werden einige MDAs bereitgestellt, wenn Sie eine Anwendung ausführen, die an einen Debugger angehängt ist. Dies gilt auch, wenn der Registrierungsschlüssel nicht hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-175">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="2e7a2-176">Sie können diese Assistenten deaktivieren, indem Sie die Datei *mdadeaktiviert. reg* ausführen, wie weiter oben in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-176">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="2e7a2-177">Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="2e7a2-177">Environment Variable</span></span>

<span data-ttu-id="2e7a2-178">Sie können die Bereitstellung von MDAs auch mithilfe der Umgebungsvariablen COMPLUS_MDA steuern, die den Registrierungsschlüssel überschreibt.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-178">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="2e7a2-179">Die Zeichenfolge COMPLUS_MDA ist eine durch Semikolons getrennte Liste von MDA-Namen und anderen Steuerzeichenfolgen, in der die Groß- und Kleinschreibung nicht beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-179">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="2e7a2-180">Bei einem Start unter einem verwalteten oder nicht verwalteten Debugger wird standardmäßig ein Satz MDAs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-180">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="2e7a2-181">Dies wird erzielt, indem die durch Semikolons getrennte Liste der MDAs, die standardmäßig unter Debuggern bereitgestellt werden, dem Wert der Umgebungsvariablen oder des Registrierungsschlüssels vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-181">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="2e7a2-182">Folgende Steuerzeichenfolgen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2e7a2-182">The special control strings are the following:</span></span>

- <span data-ttu-id="2e7a2-183">`0`: Deaktiviert alle MDAs.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-183">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="2e7a2-184">`1`: Liest MDA-Einstellungen aus *ApplicationName*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-184">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="2e7a2-185">`managedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine verwaltete ausführbare Datei unter einem Debugger gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-185">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="2e7a2-186">`unmanagedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine nicht verwaltete ausführbare Datei unter einem Debugger gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-186">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="2e7a2-187">Wenn widersprüchliche Einstellungen vorhanden sind, überschreiben die neueren Einstellungen die älteren Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2e7a2-187">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="2e7a2-188">`COMPLUS_MDA=0`: Deaktiviert alle MDAs einschließlich der MDAs, die implizit unter einem Debugger aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-188">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="2e7a2-189">`COMPLUS_MDA=gcUnmanagedToManaged` stellt `gcUnmanagedToManaged` zusätzlich zu allen MDAs bereit, die unter einem Debugger implizit aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-189">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="2e7a2-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` aktiviert `gcUnmanagedToManaged`, aber deaktiviert die MDAs, die andernfalls implizit unter einem Debugger aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="2e7a2-191">Anwendungsspezifische Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="2e7a2-191">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="2e7a2-192">In der MDA-Konfigurationsdatei für die Anwendung können Sie einige MDAs einzeln bereitstellen und konfigurieren bzw. deren Bereitstellung aufheben.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-192">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="2e7a2-193">Damit MDAs mithilfe einer Anwendungskonfigurationsdatei konfiguriert werden können, muss entweder der MDA-Registrierungsschlüssel oder die COMPLUS_MDA-Umgebungsvariable festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-193">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="2e7a2-194">Die Anwendungskonfigurationsdatei befindet sich i. d. R. im selben Verzeichnis wie die ausführbare Datei (.exe) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-194">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="2e7a2-195">Der Dateiname hat das Format *ApplicationName*.mda.config; beispielsweise notepad.exe.mda.config. In der Anwendungs Konfigurationsdatei aktivierte Assistenten verfügen möglicherweise über Attribute oder Elemente, die speziell zum Steuern des Verhaltens dieses Assistenten entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-195">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="2e7a2-196">Im folgenden Beispiel wird gezeigt, wie Sie das Marshalling aktivieren und [konfigurieren:](marshaling-mda.md)</span><span class="sxs-lookup"><span data-stu-id="2e7a2-196">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

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

<span data-ttu-id="2e7a2-197">Der `Marshaling`-MDA gibt für jeden Übergang von verwaltetem zu nicht verwaltetem Code in der Anwendung Informationen darüber aus, welcher verwaltete Typ an einen nicht verwalteten Typ gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-197">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="2e7a2-198">Der `Marshaling` MDA kann auch die Namen der Methoden-und Struktur Felder filtern, die in den untergeordneten **methodFilter** -und **fieldFilter** -Elementen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-198">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="2e7a2-199">Im folgenden Beispiel wird gezeigt, wie mehrere MDAs mithilfe ihrer Standardeinstellungen aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="2e7a2-199">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

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
> <span data-ttu-id="2e7a2-200">Wenn Sie in einer Konfigurationsdatei mehr als einen Assistenten angeben, müssen Sie diese in alphabetischer Reihenfolge aufführen.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-200">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="2e7a2-201">Wenn Sie z. B. sowohl den `virtualCERCall`-MDA als auch den `invalidCERCall`-MDA bereitstellen möchten, müssen Sie den `<invalidCERCall />`-Eintrag vor dem `<virtualCERCall />`-Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-201">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="2e7a2-202">Falls die Einträge nicht in alphabetischer Reihenfolge aufgeführt sind, wird eine Meldung mit einer unbehandelten Ausnahme zu einer ungültigen Konfigurationsdatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-202">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="2e7a2-203">MDA-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2e7a2-203">MDA exceptions</span></span>

<span data-ttu-id="2e7a2-204">Wenn ein MDA aktiviert ist, ist es auch dann aktiv, wenn der Code nicht unter einem Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-204">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="2e7a2-205">Wenn ein MDA-Ereignis ausgelöst wird, wenn kein Debugger vorhanden ist, wird die Ereignismeldung in einem Dialogfeld für unbehandelte Ausnahmen angezeigt, obwohl dies keine unbehandelte Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-205">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="2e7a2-206">Um das Anzeigen dieses Dialogfelds zu vermeiden, entfernen Sie die Einstellungen zur Aktivierung des MDA, wenn der Code nicht in einer Debugumgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-206">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="2e7a2-207">Wenn Ihr Code in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio ausgeführt wird, können Sie das Ausnahme Dialogfeld vermeiden, das für bestimmte MDA-Ereignisse angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-207">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="2e7a2-208">Wählen Sie hierzu im Menü **Debuggen** die Option **Windows**-  >  **Ausnahme Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-208">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="2e7a2-209">Erweitern Sie im Fenster " **Ausnahme Einstellungen** " die Liste der **Assistenten für verwaltetes Debuggen** , und deaktivieren Sie dann das Kontrollkästchen unter **brechen bei** ausgelöst für den jeweiligen MDA.</span><span class="sxs-lookup"><span data-stu-id="2e7a2-209">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="2e7a2-210">Sie können dieses Dialogfeld auch verwenden, um die Anzeige von MDA-Ausnahme Dialogfeldern zu *aktivieren* .</span><span class="sxs-lookup"><span data-stu-id="2e7a2-210">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="2e7a2-211">MDA-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="2e7a2-211">MDA Output</span></span>

<span data-ttu-id="2e7a2-212">Die MDA-Ausgabe ähnelt dem folgenden Beispiel, in dem die Ausgabe des `PInvokeStackImbalance` MDA angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="2e7a2-212">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="2e7a2-213">**Ein Ping-Befehl an die PInvoke-Funktion "mdatest! Mdatest. Program:: stdcall"hat den Stapel nicht ausgeglichen. Dies liegt wahrscheinlich daran, dass die verwaltete PInvoke-Signatur nicht mit der nicht verwalteten Ziel Signatur identisch ist. Überprüfen Sie, ob die Aufruf Konvention und die Parameter der PInvoke-Signatur mit der nicht verwalteten Ziel Signatur übereinstimmen.**</span><span class="sxs-lookup"><span data-stu-id="2e7a2-213">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="2e7a2-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e7a2-214">See also</span></span>

- [<span data-ttu-id="2e7a2-215">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="2e7a2-215">Debugging, Tracing, and Profiling</span></span>](index.md)
