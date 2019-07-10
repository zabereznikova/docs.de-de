---
title: ICLRMetaHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45089d1b64264e000c07603808f0c5fb1263b042
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776568"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="724ae-102">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="724ae-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="724ae-103">Enthält Methoden, die eine bestimmte Version der common Language Runtime (CLR) basierend auf ihrer Versionsnummer zurückgeben, alle installierten clrs, Listen Sie alle Laufzeiten, die in einem angegebenen Prozess geladen werden, ermitteln die CLR-Version, die zum Kompilieren einer Assembly, einen Prozess beenden mit einer sauberen Runtime beendet, und die legacy-API abfragebindung.</span><span class="sxs-lookup"><span data-stu-id="724ae-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="724ae-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="724ae-104">Methods</span></span>  
  
|<span data-ttu-id="724ae-105">Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-105">Method</span></span>|<span data-ttu-id="724ae-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="724ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="724ae-107">EnumerateInstalledRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="724ae-108">Gibt eine Enumeration, die eine gültige enthält [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellenzeiger für jede CLR-Version, die auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="724ae-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="724ae-109">EnumerateLoadedRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="724ae-110">Gibt eine Enumeration, die eine gültige enthält [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellenzeiger für jede CLR, die in einem bestimmten Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="724ae-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="724ae-111">Diese Methode ersetzt [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="724ae-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="724ae-112">ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="724ae-113">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren und beendet dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="724ae-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="724ae-114">Hat Vorrang vor den [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="724ae-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="724ae-115">GetRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="724ae-116">Ruft die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die einer bestimmten CLR-Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="724ae-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="724ae-117">Diese Methode ersetzt die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) , die mit verwendet die [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Flag.</span><span class="sxs-lookup"><span data-stu-id="724ae-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="724ae-118">GetVersionFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="724ae-119">Ruft der Assembly .NET Framework Kompilierung Originalversion (gespeichert in den Metadaten), wenn ihr Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="724ae-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="724ae-120">Diese Methode ersetzt [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="724ae-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="724ae-121">QueryLegacyV2RuntimeBinding-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="724ae-122">Gibt eine Schnittstelle, die eine Laufzeit darstellt, der ältere Aktivierungsrichtlinie, z. B. mithilfe gebunden wurde, der `useLegacyV2RuntimeActivationPolicy` -Attribut für die [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) Konfigurationsdateieintrag, durch die direkte Verwendung der Legacyaktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="724ae-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="724ae-123">RequestRuntimeLoadedNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="724ae-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="724ae-124">Einen Rückruf an den angegebenen Funktionszeiger garantiert, wenn eine CLR-Version zum ersten Mal geladen, aber noch nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="724ae-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="724ae-125">Diese Methode ersetzt [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="724ae-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="724ae-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="724ae-126">Remarks</span></span>  
 <span data-ttu-id="724ae-127">Die einzige Möglichkeit, eine Instanz dieser Schnittstelle wird durch Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion wie folgt:</span><span class="sxs-lookup"><span data-stu-id="724ae-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="724ae-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="724ae-128">Requirements</span></span>  
 <span data-ttu-id="724ae-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="724ae-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724ae-130">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="724ae-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="724ae-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="724ae-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="724ae-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="724ae-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724ae-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="724ae-133">See also</span></span>

- [<span data-ttu-id="724ae-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="724ae-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="724ae-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="724ae-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
