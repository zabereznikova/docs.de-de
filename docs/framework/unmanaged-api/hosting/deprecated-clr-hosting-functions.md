---
title: Veraltete CLR-Hostingfunktionen
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504367"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="99d8c-102">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="99d8c-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="99d8c-103">In diesem Abschnitt werden die nicht verwalteten globalen statischen Funktionen beschrieben, die von früheren Versionen der Hosting-API verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="99d8c-104">Mit Ausnahme der Infrastrukturfunktionen ( `_Cor*` Funktionen), die nur vom .NET Framework verwendet werden, wurden diese Funktionen in .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="99d8c-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="99d8c-105">Aktivierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="99d8c-105">Activation functions</span></span>  
 [<span data-ttu-id="99d8c-106">ClrCreateManagedInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="99d8c-107">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-107">Deprecated.</span></span> <span data-ttu-id="99d8c-108">Erstellt eine Instanz des angegebenen verwalteten Typs.</span><span class="sxs-lookup"><span data-stu-id="99d8c-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="99d8c-109">CoInitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="99d8c-110">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-110">Obsolete.</span></span> <span data-ttu-id="99d8c-111">Verwenden Sie zum Initialisieren des Common Language Runtime (CLR) entweder [corbindtoriuntimeex](corbindtoruntimeex-function.md) oder [corbindumcurrentruntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="99d8c-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="99d8c-112">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="99d8c-113">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-113">Deprecated.</span></span> <span data-ttu-id="99d8c-114">Stellt sicher, dass die CLR-Ausführungs-Engine in einen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="99d8c-115">Verwenden Sie stattdessen die [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="99d8c-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="99d8c-116">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="99d8c-117">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-117">Deprecated.</span></span> <span data-ttu-id="99d8c-118">Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="99d8c-119">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="99d8c-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-120">Deprecated.</span></span> <span data-ttu-id="99d8c-121">Ermöglicht es nicht verwalteten Hosts, die CLR in einen Prozess zu laden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="99d8c-122">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="99d8c-123">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-123">Deprecated.</span></span> <span data-ttu-id="99d8c-124">Lädt die CLR in einen Prozess, indem aus einer XML-Datei gelesene Versionsinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="99d8c-125">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="99d8c-126">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-126">Deprecated.</span></span> <span data-ttu-id="99d8c-127">Ermöglicht nicht verwalteten Hosts, die CLR in einen Prozess zu laden, und ermöglicht Ihnen, Flags festzulegen, um das Verhalten der CLR anzugeben.</span><span class="sxs-lookup"><span data-stu-id="99d8c-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="99d8c-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="99d8c-129">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-129">Deprecated.</span></span> <span data-ttu-id="99d8c-130">Ermöglicht Hosts, eine angegebene Version der CLR in einen Prozess zu laden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="99d8c-131">GetCORRequiredVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="99d8c-132">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-132">Deprecated.</span></span> <span data-ttu-id="99d8c-133">Ruft die erforderliche CLR-Versionsnummer ab.</span><span class="sxs-lookup"><span data-stu-id="99d8c-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="99d8c-134">GetCORSystemDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="99d8c-135">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-135">Deprecated.</span></span> <span data-ttu-id="99d8c-136">Gibt das Installationsverzeichnis der CLR zurück, die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="99d8c-137">GetRealProcAddress-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="99d8c-138">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-138">Deprecated.</span></span> <span data-ttu-id="99d8c-139">Ruft die Adresse der angegebenen Funktion ab, die aus der letzten installierten Version der CLR exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="99d8c-140">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="99d8c-141">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-141">Deprecated.</span></span> <span data-ttu-id="99d8c-142">Ruft Version und Verzeichnisinformationen über die CLR ab, die von einer Anwendung angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="99d8c-143">CLR-Versionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="99d8c-143">CLR version functions</span></span>  
 <span data-ttu-id="99d8c-144">Die Funktionen in diesem Abschnitt geben eine CLR-Version zurück; sie aktivieren nicht die CLR.</span><span class="sxs-lookup"><span data-stu-id="99d8c-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="99d8c-145">GetCORVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="99d8c-146">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-146">Deprecated.</span></span> <span data-ttu-id="99d8c-147">Gibt die Versionsnummer der CLR zurück, die im aktuellen Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="99d8c-148">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="99d8c-149">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-149">Deprecated.</span></span> <span data-ttu-id="99d8c-150">Ruft mithilfe des angegebenen Puffers die Versionsinformationen der CLR für die angegebene Datei ab.</span><span class="sxs-lookup"><span data-stu-id="99d8c-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="99d8c-151">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="99d8c-152">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-152">Deprecated.</span></span> <span data-ttu-id="99d8c-153">Ruft die Versionsnummer der CLR ab, die von der angegebenen Anwendung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="99d8c-154">Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.</span><span class="sxs-lookup"><span data-stu-id="99d8c-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="99d8c-155">GetRequestedRuntimeVersionForCLSID-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="99d8c-156">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-156">Deprecated.</span></span> <span data-ttu-id="99d8c-157">Ruft die entsprechenden CLR-Versionsinformationen für die Klasse mit der angegebenen CLSID ab.</span><span class="sxs-lookup"><span data-stu-id="99d8c-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="99d8c-158">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="99d8c-159">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-159">Deprecated.</span></span> <span data-ttu-id="99d8c-160">Ruft die Versionsnummer der CLR ab, die dem angegebenen Prozesshandle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="99d8c-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="99d8c-161">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="99d8c-162">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-162">Deprecated.</span></span> <span data-ttu-id="99d8c-163">Ermöglicht dem Host, zu bestimmen, welche Version der CLR innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="99d8c-164">Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="99d8c-164">Hosting functions</span></span>  
 [<span data-ttu-id="99d8c-165">CallFunctionShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="99d8c-166">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-166">Deprecated.</span></span> <span data-ttu-id="99d8c-167">Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="99d8c-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="99d8c-168">CoEEShutDownCOM-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="99d8c-169">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-169">Deprecated.</span></span> <span data-ttu-id="99d8c-170">Entlädt eine COM-Assembly aus dem Prozess.</span><span class="sxs-lookup"><span data-stu-id="99d8c-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="99d8c-171">CorExitProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="99d8c-172">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-172">Deprecated.</span></span> <span data-ttu-id="99d8c-173">Beendet den aktuellen nicht verwalteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="99d8c-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="99d8c-174">CorLaunchApplication-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="99d8c-175">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-175">Deprecated.</span></span> <span data-ttu-id="99d8c-176">Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="99d8c-177">CorMarkThreadInThreadPool-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="99d8c-178">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-178">Deprecated.</span></span> <span data-ttu-id="99d8c-179">Markiert den aktuell ausgeführten Thread aus dem Threadpool für die Ausführung von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="99d8c-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="99d8c-180">Ab .NET Framework Version 2.0 besitzt diese Funktion keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="99d8c-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="99d8c-181">Sie ist nicht erforderlich und kann aus dem Code entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="99d8c-182">CoUninitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="99d8c-183">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-183">Obsolete.</span></span> <span data-ttu-id="99d8c-184">Die CLR kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="99d8c-185">CoUninitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="99d8c-186">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="99d8c-187">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="99d8c-188">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-188">Deprecated.</span></span> <span data-ttu-id="99d8c-189">Erstellt ein [ICorDebug](../debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="99d8c-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="99d8c-190">CreateICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="99d8c-191">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-191">Deprecated.</span></span> <span data-ttu-id="99d8c-192">Erstellt ein [ICeeFileGen](iceefilegen-class.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="99d8c-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="99d8c-193">DestroyICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="99d8c-194">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-194">Deprecated.</span></span> <span data-ttu-id="99d8c-195">Zerstört ein [ICeeFileGen](iceefilegen-class.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="99d8c-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="99d8c-196">FExecuteInAppDomainCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="99d8c-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="99d8c-197">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-197">Deprecated.</span></span> <span data-ttu-id="99d8c-198">Zeigt auf eine Funktion, die die CLR zum Ausführen von verwaltetem Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="99d8c-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="99d8c-199">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="99d8c-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="99d8c-200">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-200">Deprecated.</span></span> <span data-ttu-id="99d8c-201">Zeigt auf eine Funktion, die die CLR aufruft, um den Host zu benachrichtigen, dass die Initialisierung gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="99d8c-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="99d8c-202">GetCLRIdentityManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="99d8c-203">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-203">Deprecated.</span></span> <span data-ttu-id="99d8c-204">Ruft einen Zeiger auf eine Schnittstelle ab, die es der CLR ermöglicht, Identitäten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="99d8c-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="99d8c-205">LoadLibraryShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="99d8c-206">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-206">Deprecated.</span></span> <span data-ttu-id="99d8c-207">Lädt die angegebene Version einer .NET Framework-DLL.</span><span class="sxs-lookup"><span data-stu-id="99d8c-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="99d8c-208">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="99d8c-209">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-209">Deprecated.</span></span> <span data-ttu-id="99d8c-210">Übersetzt einen HRESULT-Wert in eine Fehlermeldung, wobei die Standardkultur des aktuellen Threads verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99d8c-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="99d8c-211">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="99d8c-212">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-212">Deprecated.</span></span> <span data-ttu-id="99d8c-213">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="99d8c-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="99d8c-214">LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="99d8c-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="99d8c-215">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-215">Deprecated.</span></span> <span data-ttu-id="99d8c-216">Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="99d8c-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="99d8c-217">LPTHREAD_START_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="99d8c-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="99d8c-218">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-218">Deprecated.</span></span> <span data-ttu-id="99d8c-219">Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="99d8c-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="99d8c-220">RunDll32ShimW-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="99d8c-221">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-221">Deprecated.</span></span> <span data-ttu-id="99d8c-222">Führt den angegebenen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="99d8c-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="99d8c-223">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="99d8c-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="99d8c-224">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="99d8c-224">Deprecated.</span></span> <span data-ttu-id="99d8c-225">Zeigt auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle signalisiert wurde oder das Zeitlimit überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="99d8c-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="99d8c-226">Infrastrukturfunktionen</span><span class="sxs-lookup"><span data-stu-id="99d8c-226">Infrastructure functions</span></span>  
 <span data-ttu-id="99d8c-227">Die Funktionen in diesem Abschnitt gelten nur für .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99d8c-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="99d8c-228">_CorDllMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="99d8c-229">Initialisiert die CLR, sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="99d8c-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="99d8c-230">_CorExeMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="99d8c-231">Initialisiert die CLR, sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="99d8c-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="99d8c-232">_CorExeMain2-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="99d8c-233">Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus.</span><span class="sxs-lookup"><span data-stu-id="99d8c-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="99d8c-234">Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="99d8c-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="99d8c-235">_CorImageUnloading-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="99d8c-236">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="99d8c-237">_CorValidateImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="99d8c-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="99d8c-238">Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="99d8c-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d8c-239">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="99d8c-239">See also</span></span>

- [<span data-ttu-id="99d8c-240">Hosten globaler statischer .NET Framework 4-Funktionen</span><span class="sxs-lookup"><span data-stu-id="99d8c-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
