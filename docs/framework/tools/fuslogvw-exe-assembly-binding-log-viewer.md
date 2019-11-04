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
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="9e7ee-102">Fuslogvw.exe (Assembly Binding Log Viewer-Tool)</span><span class="sxs-lookup"><span data-stu-id="9e7ee-102">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>

<span data-ttu-id="9e7ee-103">In der Assemblybindungs-Protokollanzeige werden Details zu Assemblybindungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-103">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="9e7ee-104">Mit diesen Informationen lässt sich leichter diagnostizieren, weshalb zur Laufzeit in .NET Framework keine Assembly gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-104">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="9e7ee-105">Diese Fehler resultieren normalerweise aus einer Assembly, die am falschen Ort bereitgestellt wird, einem systemeigenen Abbild, das nicht mehr gültig ist, oder aus Abweichungen bei Versionsnummern oder Kulturen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-105">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="9e7ee-106">Wenn die Common Language Runtime eine Assembly nicht finden kann, wird dies in der Anwendung als <xref:System.TypeLoadException> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-106">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e7ee-107">Sie müssen "fuslogvw.exe" mit Administratorrechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-107">You must run fuslogvw.exe with administrator privileges.</span></span>

<span data-ttu-id="9e7ee-108">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="9e7ee-109">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7) mit Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7) with administrator credentials.</span></span> <span data-ttu-id="9e7ee-110">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9e7ee-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="9e7ee-111">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9e7ee-111">At the command prompt, type the following:</span></span>

```console
fuslogvw
```

<span data-ttu-id="9e7ee-112">Für jede fehlgeschlagene Assemblybindung wird ein Eintrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-112">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="9e7ee-113">Darin sind folgende Daten enthalten: welche Anwendung die Bindung initialisiert hat, für welche Assembly die Bindung bestimmt ist (Name, Version, Kultur und öffentlicher Schlüssel) sowie Datum und Uhrzeit, wann der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-113">For each failure, the viewer describes the application that initiated the bind; the assembly the bind is for, including name, version, culture and public key; and the date and time of the failure.</span></span>

### <a name="to-change-the-log-location-view"></a><span data-ttu-id="9e7ee-114">So ändern Sie die Anzeige des Protokollspeicherorts</span><span class="sxs-lookup"><span data-stu-id="9e7ee-114">To change the log location view</span></span>

1. <span data-ttu-id="9e7ee-115">Wählen Sie das Optionsfeld **Standard** aus, um Bindungsfehler für alle Anwendungstypen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-115">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="9e7ee-116">Protokolleinträge werden standardmäßig auf dem Datenträger in Verzeichnissen nach Benutzer im WinInet-Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-116">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>

2. <span data-ttu-id="9e7ee-117">Wählen Sie das Optionsfeld **Benutzerdefiniert** aus, um Bindungsfehler in dem von Ihnen angegebenen, benutzerdefinierten Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-117">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="9e7ee-118">Sie müssen den benutzerdefinierten Speicherort angeben, in dem die Protokolle von der Runtime gespeichert werden sollen, indem Sie den benutzerdefinierten Protokollspeicherort festlegen. Geben Sie dazu im Dialogfeld **Protokolleinstellungen** einen gültigen Verzeichnisnamen an.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-118">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="9e7ee-119">Dieses Verzeichnis sollte bis auf die Dateien, die von der Laufzeit generiert werden, leer sein.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-119">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="9e7ee-120">Wenn es eine ausführbare Datei enthält, die einen zu protokollierenden Fehler erzeugt, wird der Fehler nicht protokolliert, da das Tool versucht, ein Verzeichnis mit dem Namen der ausführbaren Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-120">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="9e7ee-121">Außerdem schlägt der Versuch fehl, eine ausführbare Datei vom Protokollspeicherort auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-121">In addition, an attempt to run an executable from the log location will fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e7ee-122">Anstelle des benutzerdefinierten Bindungspfads wird die Verwendung des standardmäßigen Bindungspfads empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-122">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="9e7ee-123">Der standardmäßige Bindungspfad wird während der Laufzeit im WinInet-Cache gespeichert und daher auch automatisch gelöscht. Wenn Sie einen benutzerdefinierten Bindungspfad festlegen, müssen Sie diesen selbst löschen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-123">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>

### <a name="to-view-details-about-a-specific-failure"></a><span data-ttu-id="9e7ee-124">So zeigen Sie Details für einen bestimmten Fehler an</span><span class="sxs-lookup"><span data-stu-id="9e7ee-124">To view details about a specific failure</span></span>

1. <span data-ttu-id="9e7ee-125">Markieren Sie den Anwendungsnamen des gewünschten Eintrags.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-125">Select the application name of the desired entry in the viewer.</span></span>

2. <span data-ttu-id="9e7ee-126">Klicken Sie auf die Schaltfläche **Protokolldatei anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-126">Click the **View Log** button.</span></span> <span data-ttu-id="9e7ee-127">Alternativ können Sie auch auf den markierten Eintrag doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-127">Alternately, you can double-click the selected entry.</span></span>

    <span data-ttu-id="9e7ee-128">Für den markierten Bindungsfehler werden folgende Details angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9e7ee-128">The tool displays the following details about the selected bind failure:</span></span>

    - <span data-ttu-id="9e7ee-129">Der Grund, warum die Bindung fehlgeschlagen ist, z. B. "Datei nicht gefunden" oder "Versionskonflikt".</span><span class="sxs-lookup"><span data-stu-id="9e7ee-129">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>

    - <span data-ttu-id="9e7ee-130">Daten zur Anwendung, welche die Bindung initialisiert hat, z. B. Name und Stammverzeichnis (AppBase) der Anwendung sowie gegebenenfalls eine Beschreibung des privaten Suchpfades.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-130">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>

    - <span data-ttu-id="9e7ee-131">Die Identität der gesuchten Assembly.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-131">The identity of the assembly the tool is looking for.</span></span>

    - <span data-ttu-id="9e7ee-132">Gegebenenfalls eine Beschreibung aller angewendeten Versionsrichtlinien (Anwendung, Herausgeber oder Administrator).</span><span class="sxs-lookup"><span data-stu-id="9e7ee-132">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>

    - <span data-ttu-id="9e7ee-133">Angabe, ob die Assembly im [globalen Assemblycache](../app-domains/gac.md) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-133">Whether the assembly was found in the [global assembly cache](../app-domains/gac.md).</span></span>

    - <span data-ttu-id="9e7ee-134">Eine Liste aller bei der Untersuchung verwendeten URLs.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-134">A list of all probing URLs.</span></span>

<span data-ttu-id="9e7ee-135">Das folgende Beispiel zeigt einen Protokolleintrag mit den Details einer fehlgeschlagenen Assemblybindung.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-135">The following sample log entry shows detailed information about a failed assembly bind.</span></span>

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

### <a name="to-delete-a-single-entry-from-the-log"></a><span data-ttu-id="9e7ee-136">So löschen Sie einen Eintrag aus dem Protokoll</span><span class="sxs-lookup"><span data-stu-id="9e7ee-136">To delete a single entry from the log</span></span>

1. <span data-ttu-id="9e7ee-137">Markieren Sie einen Eintrag.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-137">Select an entry in the viewer.</span></span>

2. <span data-ttu-id="9e7ee-138">Klicken Sie auf die Schaltfläche **Eintrag löschen**.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-138">Click the **Delete Entry** button.</span></span>

### <a name="to-delete-all-entries-from-the-log"></a><span data-ttu-id="9e7ee-139">So löschen Sie alle Einträge aus dem Protokoll</span><span class="sxs-lookup"><span data-stu-id="9e7ee-139">To delete all entries from the log</span></span>

- <span data-ttu-id="9e7ee-140">Klicken Sie auf die Schaltfläche **Alles löschen**.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-140">Click the **Delete All** button.</span></span>

### <a name="to-refresh-the-user-interface"></a><span data-ttu-id="9e7ee-141">So aktualisieren Sie die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="9e7ee-141">To refresh the user interface</span></span>

- <span data-ttu-id="9e7ee-142">Klicken Sie auf die Schaltfläche **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-142">Click the **Refresh** button.</span></span> <span data-ttu-id="9e7ee-143">Neue Protokolleinträge werden nicht automatisch in die Anzeige aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-143">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="9e7ee-144">Sie werden erst angezeigt, wenn Sie auf **Aktualisieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-144">You must use the **Refresh** button to display them.</span></span>

### <a name="to-change-the-log-settings"></a><span data-ttu-id="9e7ee-145">So ändern Sie die Protokolleinstellungen</span><span class="sxs-lookup"><span data-stu-id="9e7ee-145">To change the log settings</span></span>

- <span data-ttu-id="9e7ee-146">Klicken Sie auf die Schaltfläche **Einstellungen**, um das Dialogfeld **Protokolleinstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-146">Click the **Settings** button to open the **Log Settings** dialog.</span></span>

### <a name="to-view-the-about-dialog"></a><span data-ttu-id="9e7ee-147">So zeigen Sie das Dialogfeld "Info" an</span><span class="sxs-lookup"><span data-stu-id="9e7ee-147">To view the About dialog</span></span>

- <span data-ttu-id="9e7ee-148">Klicken Sie auf die Schaltfläche **Info**.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-148">Click the **About** button.</span></span>

## <a name="binding-logs-for-native-images"></a><span data-ttu-id="9e7ee-149">Binden von Protokollen für native Abbilder</span><span class="sxs-lookup"><span data-stu-id="9e7ee-149">Binding Logs for Native Images</span></span>

<span data-ttu-id="9e7ee-150">Standardmäßig protokolliert "Fuslogvw.exe" normale Assembly-Bindungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-150">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="9e7ee-151">Alternativ können Sie Assemblybindungen für native Bilder protokollieren, die mit dem [Native Image Generator (Ngen.exe)](ngen-exe-native-image-generator.md) erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-151">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).</span></span>

#### <a name="to-log-assembly-binds-for-native-images"></a><span data-ttu-id="9e7ee-152">So protokollieren Sie Assemblybindungen für systemeigene Abbildungen</span><span class="sxs-lookup"><span data-stu-id="9e7ee-152">To log assembly binds for native images</span></span>

- <span data-ttu-id="9e7ee-153">Wählen Sie in der Gruppe **Kategorien protokollieren** das Optionsfeld **Native Bilder** aus.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-153">In the **Log Categories** group, select the **Native Images** option button.</span></span>

<span data-ttu-id="9e7ee-154">Im folgenden Protokoll ist ein Fehler aufgeführt, der von einer Abhängigkeit ausgelöst wurde, die nicht vorhanden war, als das systemeigene Abbild für die Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-154">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="9e7ee-155">Wenn sich die Abhängigkeiten zur Laufzeit von den Abhängigkeiten beim Ausführen von "Ngen.exe" unterscheiden, ist das Binden an ein systemeigenes Abbild nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-155">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>

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

<span data-ttu-id="9e7ee-156">Im folgenden Protokoll ist ein Bindungsfehler für das systemeigene Abbild aufgeführt, der aufgetreten, weil sich die Sicherheitseinstellungen auf dem Computer, auf dem die Anwendung ausgeführt wurde, von den Sicherheitseinstellungen unterscheiden, die beim Erstellen des systemeigenen Abbilds festgelegt waren.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-156">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>

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

## <a name="the-log-settings-dialog"></a><span data-ttu-id="9e7ee-157">Das Dialogfeld "Protokolleinstellungen"</span><span class="sxs-lookup"><span data-stu-id="9e7ee-157">The Log Settings Dialog</span></span>

<span data-ttu-id="9e7ee-158">Sie können das Dialogfeld **Protokolleinstellungen** verwenden, um die folgenden Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-158">You can use the **Log Settings** dialog to perform the following actions.</span></span>

#### <a name="to-disable-logging"></a><span data-ttu-id="9e7ee-159">So deaktivieren Sie die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="9e7ee-159">To disable logging</span></span>

- <span data-ttu-id="9e7ee-160">Wählen Sie das Optionsfeld **Protokoll deaktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-160">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="9e7ee-161">Beachten Sie, dass diese Option in der Standardeinstellung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-161">Note that this option is selected by default.</span></span>

#### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="9e7ee-162">So protokollieren Sie Assemblybindungen in Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9e7ee-162">To log assembly binds in exceptions</span></span>

- <span data-ttu-id="9e7ee-163">Wählen Sie das Optionsfeld **In Ausnahmetext protokollieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-163">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="9e7ee-164">Nur die am wenigsten ausführlichen Fusionsprotokollinformationen werden in Ausnahmetext protokolliert.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-164">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="9e7ee-165">Um die vollständigen Informationen anzuzeigen, müssen Sie eine der anderen Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-165">To view full information, use one of the other settings.</span></span>

  <span data-ttu-id="9e7ee-166">Im wichtigen Hinweis finden Sie Informationen über Assemblys, die als domänenneutrale Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-166">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="9e7ee-167">So protokollieren Sie Assemblybindungsfehler</span><span class="sxs-lookup"><span data-stu-id="9e7ee-167">To log assembly bind failures</span></span>

- <span data-ttu-id="9e7ee-168">Wählen Sie das Optionsfeld **Fehler von Bindungen an Datenträger protokollieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-168">Select the **Log bind failures to disk** option button.</span></span>

  <span data-ttu-id="9e7ee-169">Im wichtigen Hinweis finden Sie Informationen über Assemblys, die als domänenneutrale Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-169">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="9e7ee-170">So protokollieren Sie alle Assemblybindungen</span><span class="sxs-lookup"><span data-stu-id="9e7ee-170">To log all assembly binds</span></span>

- <span data-ttu-id="9e7ee-171">Wählen Sie das Optionsfeld **Alle Bindungen an Datenträger protokollieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-171">Select the **Log all binds to disk** option button.</span></span>

  <span data-ttu-id="9e7ee-172">Im wichtigen Hinweis finden Sie Informationen über Assemblys, die als domänenneutrale Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-172">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e7ee-173">Wenn eine Assembly als domänenneutrale Assembly geladen wird, z. B. durch Festlegen der <xref:System.AppDomainSetup.LoaderOptimization%2A>-Eigenschaft auf <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> oder <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, kann das Aktivieren der Protokollierung in einigen Fällen zu Speicherverlust führen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-173">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="9e7ee-174">Dies kann der Fall sein, wenn beim Laden eines domänenneutralen Moduls in eine Anwendungsdomäne ein Protokolleintrag erfolgt und später die Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-174">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="9e7ee-175">Der Protokolleintrag wird möglicherweise erst freigegeben, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-175">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="9e7ee-176">Einige Debugger aktivieren die Protokollierung automatisch.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-176">Some debuggers automatically turn on logging.</span></span>

#### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="9e7ee-177">So aktivieren Sie einen benutzerdefinierten Protokollpfad</span><span class="sxs-lookup"><span data-stu-id="9e7ee-177">To enable a custom log path</span></span>

1. <span data-ttu-id="9e7ee-178">Wählen Sie das Optionsfeld **Benutzerdefinierten Protokollpfad aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-178">Select the **Enable custom log path** option button.</span></span>

2. <span data-ttu-id="9e7ee-179">Geben Sie den Pfad in das Textfeld **Benutzerdefinierter Protokollpfad** ein.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-179">Enter the path into the **Custom log path** text box.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7ee-180">Der [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) verwendet den Internet Explorer-Cache zum Speichern des Bindungsprotokolls.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-180">The [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="9e7ee-181">Aufgrund gelegentlicher Beschädigungen des IE-Caches ist es möglich, dass der [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) keine neuen Bindungsprotokolle mehr im Ansichtsfenster anzeigt.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-181">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="9e7ee-182">In Folge einer solchen Beschädigung kann die .NET-Bindungsinfrastruktur (Fusion) weder in das Bindungsprotokoll schreiben noch daraus lesen.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-182">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="9e7ee-183">(Dieses Problem tritt nicht auf, wenn Sie einen benutzerdefinierten Protokollpfad verwenden.)  Um die Beschädigung zu beheben und Fusion wieder das Anzeigen von Bindungsprotokollen zu ermöglichen, müssen Sie den IE-Cache löschen. Löschen Sie dazu im Dialogfeld "Internetoptionen" von Internet Explorer die temporären Internetdateien.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-183">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>
>
> <span data-ttu-id="9e7ee-184">Wenn die nicht verwaltete Anwendung die Common Language Runtime durch Implementieren der `IHostAssemblyManager`-Schnittstelle und der `IHostAssemblyStore`-Schnittstelle hostet, können Protokolleinträge nicht im WinInet-Cache gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-184">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span>  <span data-ttu-id="9e7ee-185">Um Protokolleinträge für benutzerdefinierte Hosts anzuzeigen, die diese Schnittstellen implementieren, müssen Sie einen alternativen Protokollpfad angeben.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-185">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="9e7ee-186">So aktivieren Sie die Protokollierung für im Windows-App-Container ausgeführte Apps</span><span class="sxs-lookup"><span data-stu-id="9e7ee-186">To enable logging for apps running in the Windows app container</span></span>

1. <span data-ttu-id="9e7ee-187">Aktivieren Sie einen benutzerdefinierten Protokollpfad, wie im vorherigen Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-187">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="9e7ee-188">Standardmäßig verfügen Apps, die im Windows-App-Container ausgeführt, über eingeschränkten Zugriff auf die Festplatte.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-188">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="9e7ee-189">Das Verzeichnis, das Sie angeben, erhält Lese-/Schreibzugriff für alle Apps im App-Container.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-189">The directory you specify will have read/write access for all apps in the app container.</span></span>

2. <span data-ttu-id="9e7ee-190">Aktivieren Sie das Kontrollkästchen **Immersive Protokollierung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-190">Select the **Enable immersive logging** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e7ee-191">Dieses Kontrollkästchen ist nur unter Windows 8 oder höher aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9e7ee-191">This box is enabled only on Windows 8 or later.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e7ee-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e7ee-192">See also</span></span>

- <xref:System.TypeLoadException>
- [<span data-ttu-id="9e7ee-193">Extras</span><span class="sxs-lookup"><span data-stu-id="9e7ee-193">Tools</span></span>](index.md)
- [<span data-ttu-id="9e7ee-194">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="9e7ee-194">Global Assembly Cache</span></span>](../app-domains/gac.md)
- [<span data-ttu-id="9e7ee-195">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="9e7ee-195">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="9e7ee-196">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="9e7ee-196">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
