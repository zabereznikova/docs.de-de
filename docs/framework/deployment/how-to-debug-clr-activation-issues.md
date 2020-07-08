---
title: Debuggen von CLR-Aktivierungsproblemen
description: Erfahren Sie, wie Sie Probleme bei der Aktivierung der CLR (Common Language Runtime) in .NET debuggen. Sie können CLR-Aktivierungsprotokolle einsehen und debuggen, was bei der Ermittlung von Grundursachen nützlich sein kann.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 5215e82aebf93fa8d6d1937563ab348126a01d97
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622613"
---
# <a name="how-to-debug-clr-activation-issues"></a><span data-ttu-id="ab9f9-104">Debuggen von CLR-Aktivierungsproblemen</span><span class="sxs-lookup"><span data-stu-id="ab9f9-104">How to debug CLR activation issues</span></span>

<span data-ttu-id="ab9f9-105">Wenn Sie Probleme beim Ausführen Ihrer Anwendung mit Ihrer korrekten Version der Common Language Runtime (CLR) haben, können Sie CLR-Aktivierungsprotokolle anzeigen und debuggen.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-105">If you encounter problems in getting your application to run with the correct version of the common language runtime (CLR), you can view and debug CLR activation logs.</span></span> <span data-ttu-id="ab9f9-106">Diese Protokolle können sehr nützlich beim Bestimmen der zugrunde liegenden Ursache für Probleme bei der Aktivierung sein, wenn Ihre Anwendung entweder eine andere CLR-Version als erwartet lädt oder die CLR überhaupt nicht lädt.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-106">These logs can be very useful in determining the root cause of an activation issue, when your application either loads a different CLR version than expected or doesn't load the CLR at all.</span></span> <span data-ttu-id="ab9f9-107">Im Artikel [.NET Framework-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](initialization-errors-managing-the-user-experience.md) wird die Vorgehensweise erläutert, wenn keine CLR für eine Anwendung gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-107">The [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) discusses the experience when no CLR is found for an application.</span></span>

<span data-ttu-id="ab9f9-108">Die CLR-Aktivierungsprotokollierung kann systemweit mithilfe des Registrierungsschlüssels HKEY_LOCAL_MACHINE oder einer Systemumgebungsvariable aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-108">CLR activation logging can be enabled system-wide by using an HKEY_LOCAL_MACHINE registry key or a system environment variable.</span></span> <span data-ttu-id="ab9f9-109">Das Protokoll wird generiert bis der Registrierungseintrag oder Umgebungsvariable entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-109">The log will be generated until the registry entry or the environment variable is removed.</span></span> <span data-ttu-id="ab9f9-110">Sie können alternativ einen Benutzer oder eine prozessbezogene Umgebungsvariable für die Aktivierung der Protokollierung mit einem anderen Bereich und anderer Dauer verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-110">Alternatively, you can use a user or process-local environment variable to enable logging with a different scope and duration.</span></span>

<span data-ttu-id="ab9f9-111">CLR-Aktivierungsprotokolle dürfen nicht mit [Assemblybindungsprotokollen](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) verwechselt werden. Bei diesen handelt es sich um einen vollständig anderen Protokolltyp.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-111">CLR activation logs shouldn't be confused with [assembly binding logs](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), which are entirely different.</span></span>

## <a name="to-enable-clr-activation-logging"></a><span data-ttu-id="ab9f9-112">So aktivieren Sie die CLR-Aktivierungsprotokollierung</span><span class="sxs-lookup"><span data-stu-id="ab9f9-112">To enable CLR activation logging</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="ab9f9-113">Verwendung der Registrierung</span><span class="sxs-lookup"><span data-stu-id="ab9f9-113">Using the registry</span></span>

1. <span data-ttu-id="ab9f9-114">Navigieren Sie im Registrierungs-Editor zum Ordner HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (auf einem 32-Bit-Computer) oder zu HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (auf einem 64-Bit-Computer).</span><span class="sxs-lookup"><span data-stu-id="ab9f9-114">In the Registry Editor, navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (on a 32-bit computer) or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework folder (on a 64-bit computer).</span></span>

2. <span data-ttu-id="ab9f9-115">Fügen Sie einen Zeichenfolgenwert namens `CLRLoadLogDir` hinzu, und legen Sie ihn auf den vollständigen Pfad des vorhandenen Verzeichnisses fest, wo Sie die CLR-Aktivierungsprotokolle speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-115">Add a string value named `CLRLoadLogDir`, and set it to the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

<span data-ttu-id="ab9f9-116">Die Aktivierungsprotokollierung bleibt aktiviert, bis Sie den Zeichenfolgenwert entfernen.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-116">Activation logging remains enabled until you remove the string value.</span></span>

### <a name="using-an-environment-variable"></a><span data-ttu-id="ab9f9-117">Verwenden einer Umgebungsvariablenname</span><span class="sxs-lookup"><span data-stu-id="ab9f9-117">Using an environment variable</span></span>

- <span data-ttu-id="ab9f9-118">Legen Sie eine `COMPLUS_CLRLoadLogDir`-Zeichenfolgenwert auf eine Zeichenfolge fest, die den vollständigen Pfad des vorhandenen Verzeichnisses darstellt, wo Sie die CLR-Aktivierungsprotokolle speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-118">Set the `COMPLUS_CLRLoadLogDir` environment variable to a string that represents the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

    <span data-ttu-id="ab9f9-119">So legen Sie die Umgebungsvariable fest, die ihren Bereich bestimmt:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-119">How you set the environment variable determines its scope:</span></span>

  - <span data-ttu-id="ab9f9-120">Wenn Sie sie auf Systemebene festlegen, ist die Aktivierungsprotokollierung für alle .NET Framework-Anwendungen auf diesem Computer aktiviert, bis die Umgebungsvariable entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-120">If you set it at the system level, activation logging is enabled for all .NET Framework applications on that computer until the environment variable is removed.</span></span>

  - <span data-ttu-id="ab9f9-121">Wenn Sie sie auf Benutzerebene festlegen, ist die Aktivierungsprotokollierung nur für das aktuellen Benutzerkonto aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-121">If you set it at the user level, activation logging is enabled only for the current user account.</span></span> <span data-ttu-id="ab9f9-122">Die Protokollierung wird fortgesetzt, bis die Umgebungsvariable entfernt ist.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-122">Logging continues until the environment variable is removed.</span></span>

  - <span data-ttu-id="ab9f9-123">Wenn Sie sie von innerhalb des Prozesses festlegen, bevor die CLR geladen wird, ist die Aktivierungsprotokollierung so lange aktiviert, bis der Prozess beendet ist.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-123">If you set it from within the process before loading the CLR, activation logging is enabled until the process terminates.</span></span>

  - <span data-ttu-id="ab9f9-124">Wenn Sie sie auf eine Eingabeaufforderung festlegen, bevor Sie eine Anwendung ausführen, ist die Aktivierungsprotokollierung für jede Anwendung aktiviert, die von einer Eingabeaufforderung aus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-124">If you set it at a command prompt before you run an application, activation logging is enabled for any application that is run from that command prompt.</span></span>

    <span data-ttu-id="ab9f9-125">Um z.B. Aktivierungsprotokolle im Verzeichnis „c:\clrloadlogs“ mit dem Bereich auf Prozessebene zu speichern, öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie Folgendes ein, bevor Sie die Anwendung ausführen:</span><span class="sxs-lookup"><span data-stu-id="ab9f9-125">For example, to store activation logs in the c:\clrloadlogs directory with process-level scope, open a Command Prompt window and type the following before you run the application:</span></span>

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a><span data-ttu-id="ab9f9-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab9f9-126">Example</span></span>

<span data-ttu-id="ab9f9-127">CLR-Aktivierungsprotokolle stellen eine Vielzahl von Daten über die CLR-Aktivierung und die Verwendung der Hosting-APIs der CLR bereit.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-127">CLR activation logs provide a large amount of data about CLR activation and the use of the CLR hosting APIs.</span></span> <span data-ttu-id="ab9f9-128">Der Großteil dieser Daten wird von Microsoft intern benutzt, doch einige Daten können auch für Entwickler nützlich sein, so wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-128">Most of this data is used internally by Microsoft, but some of the data can also be useful to developers, as described in this article.</span></span>

<span data-ttu-id="ab9f9-129">Das Protokoll spiegelt die Reihenfolge wider, in der die Hosting-APIs von CLR aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-129">The log reflects the order in which the CLR hosting APIs were called.</span></span> <span data-ttu-id="ab9f9-130">Es sind auch praktische Daten über die Festlegung installierter Runtimes enthalten, die auf dem Computer ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-130">It also includes useful data about the set of installed runtimes detected on the computer.</span></span> <span data-ttu-id="ab9f9-131">Das Format des CLR-Aktivierungsprotokolls ist selbst nicht dokumentiert, kann jedoch benutzt werden, um Entwicklern zu helfen, die Probleme bei der CLR-Aktivierung lösen müssen.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-131">The CLR activation log format is not itself documented, but can be used to aid developers who need to resolve CLR activation issues.</span></span>

> [!NOTE]
> <span data-ttu-id="ab9f9-132">Sie können kein Aktivierungsprotokoll öffnen, bis der Prozess, der die CLR verwendet, beendet ist.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-132">You cannot open an activation log until the process that uses the CLR has terminated.</span></span>

> [!NOTE]
> <span data-ttu-id="ab9f9-133">CLR-Aktivierungsprotokolle werden nicht lokalisiert, sondern bleiben immer in Englisch.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-133">CLR activation logs are not localized; they are always generated in the English language.</span></span>

<span data-ttu-id="ab9f9-134">Die wichtigste Information im folgenden Beispiel eines Aktivierungsprotokolls ist hervorgehoben und wird nach dem Protokoll beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-134">In the following example of an activation log, the most useful information is highlighted and described after the log.</span></span>

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- <span data-ttu-id="ab9f9-135">**CLR-Ladeprotokoll** stellt den Pfad zur ausführbaren Datei bereit, die den Prozess zum Laden des verwalteten Codes gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-135">**CLR Loading log** provides the path to the executable that started the process that loaded managed code.</span></span> <span data-ttu-id="ab9f9-136">Beachten Sie, dass dies ein nativer Host sein kann.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-136">Note that this could be a native host.</span></span>

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- <span data-ttu-id="ab9f9-137">**Installierte Runtime** ist die Reihe der auf dem Computer installierten CLR-Versionen, die Kandidaten für die Aktivierungsaufforderung sind.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-137">**Installed Runtime** is the set of CLR versions installed on the computer that are candidates for the activation request.</span></span>

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- <span data-ttu-id="ab9f9-138">**mit Version erstellt** ist die Version der CLR, die zum Erstellen der Binärdatei verwendet wurde, die einer Methode, z.B. [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md), bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-138">**built with version** is the version of the CLR that was used to build the binary that was provided to a method such as [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span></span>

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- <span data-ttu-id="ab9f9-139">**Feature-on-Demand-Installation** bezieht sich auf die Aktivierung von .NET Framework 3.5 unter Windows 8.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-139">**feature-on-demand installation** refers to enabling the .NET Framework 3.5 on Windows 8.</span></span> <span data-ttu-id="ab9f9-140">Im Artikel [.NET Framework-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](initialization-errors-managing-the-user-experience.md) finden Sie weitere Informationen zu diesem Szenario.</span><span class="sxs-lookup"><span data-stu-id="ab9f9-140">See [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) for more information about this scenario.</span></span>

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a><span data-ttu-id="ab9f9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab9f9-141">See also</span></span>

- [<span data-ttu-id="ab9f9-142">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ab9f9-142">Deployment</span></span>](index.md)
- [<span data-ttu-id="ab9f9-143">How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="ab9f9-143">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
