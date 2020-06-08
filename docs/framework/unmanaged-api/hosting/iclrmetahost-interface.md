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
ms.openlocfilehash: bb7c3659930f308328cba121c06a88cb6a95eb26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504159"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="ca634-102">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca634-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="ca634-103">Stellt Methoden bereit, die eine bestimmte Version des Common Language Runtime (CLR) basierend auf Ihrer Versionsnummer zurückgeben, alle installierten clrs auflisten, alle Laufzeiten auflisten, die in einem angegebenen Prozess geladen wurden, die CLR-Version ermitteln, die zum Kompilieren einer Assembly verwendet wird, einen Prozess mit einem fehlerhaften Herunterfahren der Laufzeit beenden und eine Abfrage der Legacy-API-Bindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ca634-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca634-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca634-104">Methods</span></span>  
  
|<span data-ttu-id="ca634-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-105">Method</span></span>|<span data-ttu-id="ca634-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ca634-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca634-107">EnumerateInstalledRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-107">EnumerateInstalledRuntimes Method</span></span>](iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="ca634-108">Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede CLR-Version enthält, die auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ca634-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="ca634-109">EnumerateLoadedRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-109">EnumerateLoadedRuntimes Method</span></span>](iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="ca634-110">Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede CLR enthält, die in einem bestimmten Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ca634-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="ca634-111">Diese Methode löst " [GetVersionFromProcess](getversionfromprocess-function.md)" aus.</span><span class="sxs-lookup"><span data-stu-id="ca634-111">This method supersedes [GetVersionFromProcess](getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="ca634-112">ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-112">ExitProcess Method</span></span>](iclrmetahost-exitprocess-method.md)|<span data-ttu-id="ca634-113">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und beendet dann den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="ca634-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="ca634-114">Ersetzt die [CorExitProcess](corexitprocess-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="ca634-114">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="ca634-115">GetRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-115">GetRuntime Method</span></span>](iclrmetahost-getruntime-method.md)|<span data-ttu-id="ca634-116">Ruft die [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle ab, die einer bestimmten CLR-Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="ca634-116">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="ca634-117">Diese Methode ersetzt die [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion, die mit dem [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) -Flag verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ca634-117">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="ca634-118">GetVersionFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-118">GetVersionFromFile Method</span></span>](iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="ca634-119">Ruft die ursprüngliche .NET Framework Kompilierungs Version der Assembly (gespeichert in den Metadaten) ab, wenn Ihr Dateipfad angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ca634-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="ca634-120">Diese Methode ersetzt [GetFileVersion](getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="ca634-120">This method supersedes [GetFileVersion](getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="ca634-121">QueryLegacyV2RuntimeBinding-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-121">QueryLegacyV2RuntimeBinding Method</span></span>](iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="ca634-122">Gibt eine-Schnittstelle zurück, die eine Laufzeit darstellt, an die die Legacy Aktivierungs Richtlinie gebunden wurde, z. b. durch die Verwendung des- `useLegacyV2RuntimeActivationPolicy` Attributs für den Eintrag der [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) Konfigurationsdatei, durch direkte Verwendung der Legacy-Aktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="ca634-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="ca634-123">RequestRuntimeLoadedNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="ca634-123">RequestRuntimeLoadedNotification Method</span></span>](iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="ca634-124">Garantiert einen Rückruf für den angegebenen Funktionszeiger, wenn eine CLR-Version zum ersten Mal geladen, aber noch nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ca634-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="ca634-125">Diese Methode ersetzt [LockClrVersion](lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="ca634-125">This method supersedes [LockClrVersion](lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca634-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ca634-126">Remarks</span></span>  
 <span data-ttu-id="ca634-127">Sie können eine Instanz dieser Schnittstelle nur abrufen, indem Sie die [CLRCreateInstance](clrcreateinstance-function.md) -Funktion wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="ca634-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ca634-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ca634-128">Requirements</span></span>  
 <span data-ttu-id="ca634-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca634-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca634-130">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="ca634-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca634-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ca634-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca634-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca634-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca634-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ca634-133">See also</span></span>

- [<span data-ttu-id="ca634-134">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca634-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ca634-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="ca634-135">Hosting</span></span>](index.md)
