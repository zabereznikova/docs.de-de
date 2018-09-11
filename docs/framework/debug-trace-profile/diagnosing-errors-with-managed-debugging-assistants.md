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
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269188"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="011a5-102">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="011a5-102">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="011a5-103">MDAs (Managed Debugging Assistants, Assistenten für verwaltetes Debuggen) sind Hilfsmittel für das Debuggen, die mit der CLR (Common Language Runtime) zusammenarbeiten, um Informationen zum Laufzeitzustand bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="011a5-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="011a5-104">Die Assistenten generieren Informationsmeldungen über Laufzeitereignisse, die Sie auf keine andere Art abfangen können.</span><span class="sxs-lookup"><span data-stu-id="011a5-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="011a5-105">Sie können MDAs verwenden, um schwer aufzufindende Anwendungsfehler zu isolieren, die bei Übergängen zwischen verwaltetem und nicht verwaltetem Code auftreten.</span><span class="sxs-lookup"><span data-stu-id="011a5-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="011a5-106">Sie können [aktivieren oder deaktivieren Sie](#enable-and-disable-mdas) alle MDAs, die durch Hinzufügen eines Schlüssels in der Windows-Registrierung oder durch Festlegen einer Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="011a5-106">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="011a5-107">Sie können bestimmte MDAs mithilfe von Anwendungskonfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="011a5-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="011a5-108">In der Konfigurationsdatei der Anwendung können Sie zusätzliche Konfigurationseinstellungen für einige der MDAs festlegen.</span><span class="sxs-lookup"><span data-stu-id="011a5-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="011a5-109">Da die Konfigurationsdateien beim Laden der Laufzeit analysiert werden, müssen Sie den MDA bereitstellen, bevor die verwaltete Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="011a5-110">Sie können ihn nicht für Anwendungen bereitstellen, die bereits gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="011a5-110">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="011a5-111">Die folgende Tabelle enthält die MDAs im Lieferumfang mit .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="011a5-111">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="011a5-112">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="011a5-112">asynchronousThreadAbort</span></span>](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[<span data-ttu-id="011a5-113">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="011a5-113">bindingFailure</span></span>](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|
|[<span data-ttu-id="011a5-114">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="011a5-114">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="011a5-115">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="011a5-115">contextSwitchDeadlock</span></span>](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="011a5-116">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="011a5-116">dangerousThreadingAPI</span></span>](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[<span data-ttu-id="011a5-117">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="011a5-117">dateTimeInvalidLocalFormat</span></span>](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="011a5-118">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="011a5-118">dirtyCastAndCallOnInterface</span></span>](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="011a5-119">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="011a5-119">disconnectedContext</span></span>](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|
|[<span data-ttu-id="011a5-120">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="011a5-120">dllMainReturnsFalse</span></span>](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[<span data-ttu-id="011a5-121">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="011a5-121">exceptionSwallowedOnCallFromCom</span></span>](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="011a5-122">failedQI</span><span class="sxs-lookup"><span data-stu-id="011a5-122">failedQI</span></span>](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[<span data-ttu-id="011a5-123">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="011a5-123">fatalExecutionEngineError</span></span>](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="011a5-124">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="011a5-124">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="011a5-125">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="011a5-125">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="011a5-126">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="011a5-126">illegalPrepareConstrainedRegion</span></span>](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="011a5-127">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="011a5-127">invalidApartmentStateChange</span></span>](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="011a5-128">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="011a5-128">invalidCERCall</span></span>](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[<span data-ttu-id="011a5-129">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="011a5-129">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="011a5-130">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="011a5-130">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[<span data-ttu-id="011a5-131">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="011a5-131">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|
|[<span data-ttu-id="011a5-132">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="011a5-132">invalidMemberDeclaration</span></span>](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[<span data-ttu-id="011a5-133">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="011a5-133">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="011a5-134">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="011a5-134">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[<span data-ttu-id="011a5-135">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="011a5-135">jitCompilationStart</span></span>](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|
|[<span data-ttu-id="011a5-136">loaderLock</span><span class="sxs-lookup"><span data-stu-id="011a5-136">loaderLock</span></span>](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[<span data-ttu-id="011a5-137">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="011a5-137">loadFromContext</span></span>](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|
|[<span data-ttu-id="011a5-138">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="011a5-138">marshalCleanupError</span></span>](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[<span data-ttu-id="011a5-139">marshaling</span><span class="sxs-lookup"><span data-stu-id="011a5-139">marshaling</span></span>](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|
|[<span data-ttu-id="011a5-140">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="011a5-140">memberInfoCacheCreation</span></span>](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[<span data-ttu-id="011a5-141">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="011a5-141">moduloObjectHashcode</span></span>](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="011a5-142">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="011a5-142">nonComVisibleBaseClass</span></span>](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="011a5-143">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="011a5-143">notMarshalable</span></span>](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|
|[<span data-ttu-id="011a5-144">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="011a5-144">openGenericCERCall</span></span>](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[<span data-ttu-id="011a5-145">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="011a5-145">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|
|[<span data-ttu-id="011a5-146">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="011a5-146">pInvokeLog</span></span>](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[<span data-ttu-id="011a5-147">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="011a5-147">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="011a5-148">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="011a5-148">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[<span data-ttu-id="011a5-149">reentrancy</span><span class="sxs-lookup"><span data-stu-id="011a5-149">reentrancy</span></span>](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|
|[<span data-ttu-id="011a5-150">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="011a5-150">releaseHandleFailed</span></span>](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[<span data-ttu-id="011a5-151">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="011a5-151">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|
|[<span data-ttu-id="011a5-152">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="011a5-152">streamWriterBufferedDataLost</span></span>](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="011a5-153">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="011a5-153">virtualCERCall</span></span>](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|

<span data-ttu-id="011a5-154">Standardmäßig aktiviert .NET Framework eine Teilmenge von MDAs für alle verwalteten Debugger.</span><span class="sxs-lookup"><span data-stu-id="011a5-154">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="011a5-155">Sie können den Standardsatz in Visual Studio, durch Auswahl anzeigen **Windows** > **Ausnahmeeinstellungen** auf die **Debuggen** Menü und dann erweitern die **Managed Debugging Assistants** Liste.</span><span class="sxs-lookup"><span data-stu-id="011a5-155">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Fenster Ausnahmeeinstellungen in Visual Studio](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="011a5-157">Aktivieren und Deaktivieren von MDAs</span><span class="sxs-lookup"><span data-stu-id="011a5-157">Enable and Disable MDAs</span></span>

<span data-ttu-id="011a5-158">Sie können MDAs mit einem Registrierungsschlüssel, einer Umgebungsvariablen und Anwendungskonfigurationseinstellungen bereitstellen sowie deren Bereitstellung aufheben.</span><span class="sxs-lookup"><span data-stu-id="011a5-158">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="011a5-159">Sie müssen entweder den Registrierungsschlüssel oder die Umgebungsvariable für die Verwendung der Anwendungskonfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="011a5-159">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="011a5-160">Anstelle der Bereitstellung von MDAs, können Sie verhindern, dass Visual Studio die MDA-Dialogfeld angezeigt, wenn eine MDA-Benachrichtigung empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-160">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="011a5-161">Zu diesem Zweck wählen **Windows** > **Ausnahmeeinstellungen** auf die **Debuggen** Menü erweitern Sie die **Managed Debugging Assistants**aufzulisten, und aktivieren bzw. deaktivieren Sie die **unterbrechen Wenn ausgelöst** das Kontrollkästchen für den jeweiligen MDA.</span><span class="sxs-lookup"><span data-stu-id="011a5-161">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="011a5-162">-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="011a5-162">Registry Key</span></span>

<span data-ttu-id="011a5-163">Um MDAs zu aktivieren, fügen die **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\MDA** Unterschlüssel (Typ: REG_SZ, Wert 1) in der Windows-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="011a5-163">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="011a5-164">Kopieren Sie im folgenden Beispiel wird in eine Textdatei namens *"MDAEnable.reg"*. Öffnen Sie den Windows-Registrierungs-Editor (RegEdit.exe), und von der **Datei** Menü **Import**.</span><span class="sxs-lookup"><span data-stu-id="011a5-164">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="011a5-165">Wählen Sie die *"MDAEnable.reg"* Datei, die auf diesem Computer MDAs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="011a5-165">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="011a5-166">Durch Festlegen des Unterschlüssels Zeichenfolgenwert eines **1** (nicht DWORD-Wert, der **1**) ermöglicht das Lesen der MDA-Einstellungen aus der *ApplicationName.suffix*. mda.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="011a5-166">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="011a5-167">Der MDA-Konfigurationsdatei für Notepad würde z. B. den Namen notepad.exe.mda.config sein.</span><span class="sxs-lookup"><span data-stu-id="011a5-167">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="011a5-168">Führt der Computer eine 32-Bit-Anwendung auf einem 64-Bit-System aus, dann sollte der MDA-Schlüssel folgendermaßen festgelegt sein:</span><span class="sxs-lookup"><span data-stu-id="011a5-168">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="011a5-169">Finden Sie unter [anwendungsspezifischen Konfigurationseinstellungen](#application-specific-configuration-settings) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="011a5-169">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="011a5-170">Die Registrierungseinstellung kann durch die COMPLUS_MDA-Umgebungsvariable überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="011a5-170">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="011a5-171">Finden Sie unter [Umgebungsvariable](#environment-variable) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="011a5-171">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="011a5-172">Um MDAs zu deaktivieren, legen Sie den MDA-Unterschlüssel auf **0** (null), mit der Windows-Registrierungs-Editor.</span><span class="sxs-lookup"><span data-stu-id="011a5-172">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="011a5-173">In der Standardeinstellung werden einige MDAs bereitgestellt, wenn Sie eine Anwendung ausführen, die an einen Debugger angehängt ist. Dies gilt auch, wenn der Registrierungsschlüssel nicht hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="011a5-173">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="011a5-174">Sie können dieser Assistenten deaktivieren, indem Sie Ausführung der *"MDADisable.reg"* wie weiter oben in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="011a5-174">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="011a5-175">Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="011a5-175">Environment Variable</span></span>

<span data-ttu-id="011a5-176">Sie können die Bereitstellung von MDAs auch mithilfe der Umgebungsvariablen COMPLUS_MDA steuern, die den Registrierungsschlüssel überschreibt.</span><span class="sxs-lookup"><span data-stu-id="011a5-176">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="011a5-177">Die Zeichenfolge COMPLUS_MDA ist eine durch Semikolons getrennte Liste von MDA-Namen und anderen Steuerzeichenfolgen, in der die Groß- und Kleinschreibung nicht beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-177">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="011a5-178">Bei einem Start unter einem verwalteten oder nicht verwalteten Debugger wird standardmäßig ein Satz MDAs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="011a5-178">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="011a5-179">Dies wird erzielt, indem die durch Semikolons getrennte Liste der MDAs, die standardmäßig unter Debuggern bereitgestellt werden, dem Wert der Umgebungsvariablen oder des Registrierungsschlüssels vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-179">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="011a5-180">Folgende Steuerzeichenfolgen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="011a5-180">The special control strings are the following:</span></span>

- <span data-ttu-id="011a5-181">`0`: Deaktiviert alle MDAs.</span><span class="sxs-lookup"><span data-stu-id="011a5-181">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="011a5-182">`1`: Liest MDA-Einstellungen aus *ApplicationName*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="011a5-182">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="011a5-183">`managedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine verwaltete ausführbare Datei unter einem Debugger gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-183">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="011a5-184">`unmanagedDebugger`: Aktiviert ausdrücklich alle MDAs, die implizit aktiviert werden, wenn eine nicht verwaltete ausführbare Datei unter einem Debugger gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-184">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="011a5-185">Wenn widersprüchliche Einstellungen vorhanden sind, überschreiben die neueren Einstellungen die älteren Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="011a5-185">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="011a5-186">`COMPLUS_MDA=0`: Deaktiviert alle MDAs einschließlich der MDAs, die implizit unter einem Debugger aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="011a5-186">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="011a5-187">`COMPLUS_MDA=gcUnmanagedToManaged` stellt `gcUnmanagedToManaged` zusätzlich zu allen MDAs bereit, die unter einem Debugger implizit aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="011a5-187">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="011a5-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` aktiviert `gcUnmanagedToManaged`, aber deaktiviert die MDAs, die andernfalls implizit unter einem Debugger aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="011a5-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="011a5-189">Anwendungsspezifische Einstellungen</span><span class="sxs-lookup"><span data-stu-id="011a5-189">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="011a5-190">In der MDA-Konfigurationsdatei für die Anwendung können Sie einige MDAs einzeln bereitstellen und konfigurieren bzw. deren Bereitstellung aufheben.</span><span class="sxs-lookup"><span data-stu-id="011a5-190">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="011a5-191">Damit MDAs mithilfe einer Anwendungskonfigurationsdatei konfiguriert werden können, muss entweder der MDA-Registrierungsschlüssel oder die COMPLUS_MDA-Umgebungsvariable festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="011a5-191">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="011a5-192">Die Anwendungskonfigurationsdatei befindet sich i. d. R. im selben Verzeichnis wie die ausführbare Datei (.exe) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="011a5-192">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="011a5-193">Der Dateiname hat das Format *ApplicationName*.mda.config, z.B. „notepad.exe.mda.config“. Assistenten, die über die Anwendungskonfigurationsdatei bereitgestellt werden, können Attribute oder Elemente aufweisen, die speziell für die Steuerung des Verhaltens dieses Assistenten vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="011a5-193">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="011a5-194">Das folgende Beispiel zeigt, wie Sie zum Aktivieren und Konfigurieren der [Marshalling](../../../docs/framework/debug-trace-profile/marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="011a5-194">The following example shows how to enable and configure the [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md):</span></span>

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

<span data-ttu-id="011a5-195">Der `Marshaling`-MDA gibt für jeden Übergang von verwaltetem zu nicht verwaltetem Code in der Anwendung Informationen darüber aus, welcher verwaltete Typ an einen nicht verwalteten Typ gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-195">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="011a5-196">Die `Marshaling` MDA kann auch filtern, die Namen der Methoden- und Strukturfelder im angegebenen die **MethodFilter** und **FieldFilter** untergeordnete Elemente, bzw.</span><span class="sxs-lookup"><span data-stu-id="011a5-196">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="011a5-197">Das folgende Beispiel zeigt, wie Sie mehrere MDAs mithilfe ihrer Standardeinstellungen:</span><span class="sxs-lookup"><span data-stu-id="011a5-197">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

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
> <span data-ttu-id="011a5-198">Wenn Sie in einer Konfigurationsdatei mehr als einen Assistenten angeben, müssen Sie diese in alphabetischer Reihenfolge aufführen.</span><span class="sxs-lookup"><span data-stu-id="011a5-198">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="011a5-199">Wenn Sie z. B. sowohl den `virtualCERCall`-MDA als auch den `invalidCERCall`-MDA bereitstellen möchten, müssen Sie den `<invalidCERCall />`-Eintrag vor dem `<virtualCERCall />`-Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="011a5-199">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="011a5-200">Falls die Einträge nicht in alphabetischer Reihenfolge aufgeführt sind, wird eine Meldung mit einer unbehandelten Ausnahme zu einer ungültigen Konfigurationsdatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="011a5-200">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="011a5-201">MDA-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="011a5-201">MDA exceptions</span></span>

<span data-ttu-id="011a5-202">Wenn ein MDA aktiviert ist, ist er aktiv selbst wenn Ihr Code nicht unter einem Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-202">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="011a5-203">Wenn ein MDA-Ereignis ausgelöst wird, wenn kein Debugger vorhanden ist, wird die Ereignismeldung in einem Dialogfeld für unbehandelte Ausnahmen angezeigt, obwohl dies keine unbehandelte Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="011a5-203">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="011a5-204">Um das Anzeigen dieses Dialogfelds zu vermeiden, entfernen Sie die Einstellungen zur Aktivierung des MDA, wenn der Code nicht in einer Debugumgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="011a5-204">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="011a5-205">Wenn Ihr Code in der integrierten Entwicklungsumgebung (IDE) von Visual Studio ausgeführt wird, können Sie das Ausnahmedialogfeld vermeiden, das für bestimmte MDA-Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="011a5-205">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="011a5-206">In diesem Fall tun, auf die **Debuggen** Menü wählen **Windows** > **Ausnahmeeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="011a5-206">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="011a5-207">In der **Ausnahmeeinstellungen** Fenster, erweitern Sie die **Managed Debugging Assistants** aus, und deaktivieren Sie dann die **unterbrechen Wenn ausgelöst** das Kontrollkästchen für den jeweiligen MDA.</span><span class="sxs-lookup"><span data-stu-id="011a5-207">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="011a5-208">Sie können dieses Dialogfeld auch verwenden *aktivieren* die Anzeige von MDA-ausnahmedialogfeldern.</span><span class="sxs-lookup"><span data-stu-id="011a5-208">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="011a5-209">MDA-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="011a5-209">MDA Output</span></span>

<span data-ttu-id="011a5-210">MDA sieht in etwa wie im folgenden Beispiel, in dem die Ausgabe zeigt die `PInvokeStackImbalance` MDA:</span><span class="sxs-lookup"><span data-stu-id="011a5-210">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="011a5-211">**Ein Aufruf von PInvoke-Funktion "MDATest! MDATest.Program::StdCall' hat einen nicht ausgeglichenen Stapel. Dies ist wahrscheinlich, weil die verwaltete PInvoke-Signatur nicht die Signatur nicht verwaltetes Ziel übereinstimmt. Überprüfen Sie, dass die Aufrufkonvention und die Parameter von PInvoke-Signatur die nicht verwalteten Ziel-Signatur entsprechen.**</span><span class="sxs-lookup"><span data-stu-id="011a5-211">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="011a5-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="011a5-212">See also</span></span>

- [<span data-ttu-id="011a5-213">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="011a5-213">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
