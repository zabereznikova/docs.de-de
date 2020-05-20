---
title: CorBindToRuntimeEx-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
ms.openlocfilehash: dcf2ce8bdb7cec1f567e548ff3314e160fffe9fd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616631"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="89e60-102">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="89e60-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="89e60-103">Ermöglicht es nicht verwalteten Hosts, die Common Language Runtime (CLR) in einen Prozess zu laden.</span><span class="sxs-lookup"><span data-stu-id="89e60-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="89e60-104">Die [CorBindToRuntime](corbindtoruntime-function.md) -Funktion und die- `CorBindToRuntimeEx` Funktion führen denselben Vorgang aus, aber mit der- `CorBindToRuntimeEx` Funktion können Sie Flags festlegen, um das Verhalten der CLR anzugeben.</span><span class="sxs-lookup"><span data-stu-id="89e60-104">The [CorBindToRuntime](corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="89e60-105">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="89e60-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="89e60-106">Diese Funktion verwendet einen Parametersatz, der einem Host die folgenden Aktionen ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="89e60-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="89e60-107">Angeben der Version der zu ladenden Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="89e60-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="89e60-108">Angeben, ob der Serverbuild oder der Arbeitsstationsbuild geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="89e60-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="89e60-109">Steuern, ob die gleichzeitige oder nicht gleichzeitige Garbage Collection ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89e60-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89e60-110">Die gleichzeitige Garbage Collection wird nicht in Anwendungen unterstützt, die den WOW64 x86-Emulator auf 64-Bit-Systemen mit einer Implementierung der Intel Itanium-Architektur (früher als IA-64 bezeichnet) ausführen.</span><span class="sxs-lookup"><span data-stu-id="89e60-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="89e60-111">Weitere Informationen zur Verwendung von WOW64 auf 64-Bit-Windows-Systemen finden Sie unter [Ausführen von 32-Bit-Anwendungen](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="89e60-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="89e60-112">Steuern, ob Assemblys als domänenneutral geladen werden.</span><span class="sxs-lookup"><span data-stu-id="89e60-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="89e60-113">Rufen Sie einen Schnittstellen Zeiger auf ein [ICorRuntimeHost](icorruntimehost-interface.md) -Element ab, das verwendet werden kann, um zusätzliche Optionen zum Konfigurieren einer Instanz der CLR vor dem Start festzulegen.</span><span class="sxs-lookup"><span data-stu-id="89e60-113">Obtain an interface pointer to an [ICorRuntimeHost](icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e60-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="89e60-114">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e60-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="89e60-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="89e60-116">[in] Eine Zeichenfolge, die die Version der zu ladenden CLR beschreibt.</span><span class="sxs-lookup"><span data-stu-id="89e60-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="89e60-117">Eine Versionsnummer im .NET Framework besteht aus vier Teilen, die durch Zeiträume getrennt sind: *Major. Minor. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="89e60-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="89e60-118">Die als `pwszVersion` übergebene Zeichenfolge muss mit dem Buchstaben "v" beginnen, auf den die ersten drei Teile der Versionsnummer folgen (z. B. "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="89e60-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="89e60-119">Einige Versionen der CLR werden mit einer Richtlinienanweisung installiert, welche die Kompatibilität mit früheren Versionen der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="89e60-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="89e60-120">In der Standardeinstellung wertet das Startmodul `pwszVersion` anhand von Richtlinienanweisungen aus und lädt die neueste Version der Common Language Runtime, die mit der angeforderten Version kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="89e60-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="89e60-121">Ein Host kann erzwingen, dass das Startmodul die Richtlinienauswertung überspringt und genau die in `pwszVersion` angegebene Version lädt, indem wie unten beschrieben der Wert `STARTUP_LOADER_SAFEMODE` für den `startupFlags`-Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="89e60-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="89e60-122">Wenn der Aufrufer NULL für `pwszVersion` angibt, identifiziert `CorBindToRuntimeEx` den Satz der installierten Laufzeiten, deren Versionsnummer niedriger als die .NET Framework 4-Laufzeit ist, und lädt die neueste Version der Laufzeit von diesem Satz.</span><span class="sxs-lookup"><span data-stu-id="89e60-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="89e60-123">Sie lädt nicht .NET Framework 4 oder höher und schlägt fehl, wenn keine frühere Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="89e60-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="89e60-124">Beachten Sie, dass bei einer Übergabe von NULL der Host nicht steuern kann, welche Version der Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="89e60-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="89e60-125">Auch wenn dieser Ansatz in einigen Szenarien angemessen sein kann, wird das Angeben einer bestimmten zu ladenden Version durch den Host dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="89e60-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="89e60-126">[in] Eine Zeichenfolge, die angibt, ob der Serverbuild oder der Arbeitsstationsbuild der CLR geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="89e60-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="89e60-127">Gültige Werte sind `svr` und `wks`.</span><span class="sxs-lookup"><span data-stu-id="89e60-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="89e60-128">Der Serverbuild wurde so optimiert, dass mehrere Prozessoren zur Ausführung der Garbage Collection genutzt werden können. Der Arbeitsstationsbuild wurde für die Ausführung von Clientanwendungen auf einem Computer mit einem einzelnen Prozessor optimiert.</span><span class="sxs-lookup"><span data-stu-id="89e60-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="89e60-129">Wenn `pwszBuildFlavor` auf NULL festgelegt ist, wird der Arbeitsstations Build geladen.</span><span class="sxs-lookup"><span data-stu-id="89e60-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="89e60-130">Bei der Ausführung auf einem Computer mit einem einzelnen Prozessor wird der Arbeitsstations Build immer geladen, auch wenn `pwszBuildFlavor` auf festgelegt ist `svr` .</span><span class="sxs-lookup"><span data-stu-id="89e60-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="89e60-131">Wenn jedoch `pwszBuildFlavor` auf festgelegt ist `svr` und gleichzeitige Garbage Collection angegeben ist (siehe Beschreibung des `startupFlags` Parameters), wird der Serverbuild geladen.</span><span class="sxs-lookup"><span data-stu-id="89e60-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="89e60-132">in Eine Kombination von Werten der [STARTUP_FLAGS](startup-flags-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="89e60-132">[in] A combination of values of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="89e60-133">Diese Flags steuern die gleichzeitige Garbage Collection, domänenneutralen Code und das Verhalten des `pwszVersion`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="89e60-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="89e60-134">Wenn kein Flag festgelegt ist, gilt als Standardwert die Einzeldomäne.</span><span class="sxs-lookup"><span data-stu-id="89e60-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="89e60-135">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="89e60-135">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="89e60-136">Beschreibungen dieser Flags finden Sie in der [STARTUP_FLAGS](startup-flags-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="89e60-136">For descriptions of these flags, see the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="89e60-137">in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="89e60-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="89e60-138">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="89e60-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="89e60-139">[in] Die `IID` der angeforderten Schnittstelle aus `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="89e60-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="89e60-140">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="89e60-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="89e60-141">[out] Der zurückgegebene Schnittstellenzeiger auf `riid`.</span><span class="sxs-lookup"><span data-stu-id="89e60-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89e60-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89e60-142">Remarks</span></span>  
 <span data-ttu-id="89e60-143">Wenn `pwszVersion` eine Laufzeitversion angibt, die nicht vorhanden ist, gibt `CorBindToRuntimeEx` den HRESULT-Wert CLR_E_SHIM_RUNTIMELOAD zurück.</span><span class="sxs-lookup"><span data-stu-id="89e60-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="89e60-144">Ausführungskontext und Übergabe der Windows-Identität</span><span class="sxs-lookup"><span data-stu-id="89e60-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="89e60-145">In Version 1 der CLR wird das <xref:System.Security.Principal.WindowsIdentity>-Objekt nicht über asynchrone Punkte wie neue Threads, Threadpools oder Timerrückrufe übergeben.</span><span class="sxs-lookup"><span data-stu-id="89e60-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="89e60-146">In Version 2.0 der CLR umschließt ein <xref:System.Threading.ExecutionContext>-Objekt einige Informationen zum aktuell ausgeführten Thread und übergibt ihn über einen asynchronen Punkt, aber innerhalb der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="89e60-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="89e60-147">Auf ähnliche Weise wird auch das <xref:System.Security.Principal.WindowsIdentity>-Objekt über einen asynchronen Punkt übergeben.</span><span class="sxs-lookup"><span data-stu-id="89e60-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="89e60-148">Deshalb wird auch der aktuelle Identitätswechsel auf dem Thread (sofern vorhanden) übergeben.</span><span class="sxs-lookup"><span data-stu-id="89e60-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="89e60-149">Sie können den Fluss auf zwei Weisen ändern:</span><span class="sxs-lookup"><span data-stu-id="89e60-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="89e60-150">Durch Ändern der <xref:System.Threading.ExecutionContext>-Einstellungen wird die Übergabe für einzelne Threads unterdrückt (siehe die Methoden <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A> und <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).</span><span class="sxs-lookup"><span data-stu-id="89e60-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="89e60-151">Durch Ändern des Prozessstandardmodus in den Kompatibilitätsmodus für Version 1; hier wird das <xref:System.Security.Principal.WindowsIdentity>-Objekt nicht über asynchrone Punkte übergeben, unabhängig von den <xref:System.Threading.ExecutionContext>-Einstellungen des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="89e60-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="89e60-152">Wie der Standardmodus geändert wird, hängt davon ab, ob Sie zum Laden der CLR eine verwaltete ausführbare Datei oder eine nicht verwaltete Hostschnittstelle verwenden:</span><span class="sxs-lookup"><span data-stu-id="89e60-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="89e60-153">Bei verwalteten ausführbaren Dateien müssen Sie das- `enabled` Attribut des [ \< legacyidentitäts->](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) Elements auf festlegen `true` .</span><span class="sxs-lookup"><span data-stu-id="89e60-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="89e60-154">Legen Sie bei nicht verwalteten Hostschnittstellen das `STARTUP_LEGACY_IMPERSONATION`-Flag im `startupFlags`-Parameter fest, wenn Sie die `CorBindToRuntimeEx`-Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="89e60-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="89e60-155">Der Kompatibilitätsmodus für Version 1 gilt für den gesamten Prozess und alle Anwendungsdomänen im Prozess.</span><span class="sxs-lookup"><span data-stu-id="89e60-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e60-156">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89e60-156">Requirements</span></span>  
 <span data-ttu-id="89e60-157">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e60-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e60-158">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="89e60-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89e60-159">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="89e60-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89e60-160">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e60-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e60-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89e60-161">See also</span></span>

- [<span data-ttu-id="89e60-162">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="89e60-162">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="89e60-163">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="89e60-163">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="89e60-164">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="89e60-164">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="89e60-165">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="89e60-165">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="89e60-166">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89e60-166">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="89e60-167">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="89e60-167">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
