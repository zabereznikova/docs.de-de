---
title: IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetNonHostStoreAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35e22e186b290cc4242275976f5109b73e2cf068
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="e6370-102">IHostAssemblyManager::GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="e6370-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="e6370-103">Ruft einen Schnittstellenzeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die die Liste der Assemblys, die der Host erwartet, die common Language Runtime (CLR dass) geladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6370-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6370-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6370-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6370-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6370-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="e6370-106">[out] Ein Zeiger auf die Adresse des ein `ICLRAssemblyReferenceList` , enthält eine Liste der Verweise auf Assemblys, die der Host die CLR geladen erwartet.</span><span class="sxs-lookup"><span data-stu-id="e6370-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6370-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e6370-107">Return Value</span></span>  
  
|<span data-ttu-id="e6370-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6370-108">HRESULT</span></span>|<span data-ttu-id="e6370-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6370-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6370-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6370-110">S_OK</span></span>|<span data-ttu-id="e6370-111">`GetNonHostStoreAssemblies`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e6370-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="e6370-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="e6370-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6370-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e6370-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6370-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6370-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6370-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e6370-115">The call timed out.</span></span>|  
|<span data-ttu-id="e6370-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6370-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6370-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e6370-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6370-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6370-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6370-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e6370-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6370-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6370-120">E_FAIL</span></span>|<span data-ttu-id="e6370-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e6370-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6370-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e6370-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6370-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e6370-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e6370-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e6370-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e6370-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für die angeforderte erstellen `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="e6370-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6370-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6370-126">Remarks</span></span>  
 <span data-ttu-id="e6370-127">Die CLR löst Verweise mithilfe der folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="e6370-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="e6370-128">Er fragt zunächst die Liste der Assemblyverweise zurückgegebenes `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="e6370-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="e6370-129">Wenn die Assembly in der Liste angezeigt wird, wird die CLR auf die normalerweise gebunden.</span><span class="sxs-lookup"><span data-stu-id="e6370-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="e6370-130">Wenn die Assembly nicht in der Liste angezeigt, und der Host eine Implementierung der stellt [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), die CLR ruft [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) auf den Host ermöglichen die die Assembly zum Binden an.</span><span class="sxs-lookup"><span data-stu-id="e6370-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="e6370-131">Andernfalls schlägt die CLR zum Binden an die Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="e6370-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="e6370-132">Wenn bei der Host `ppReferenceList` Aufrufe um zu null, die erste CLR-Prüfpunkte im globalen Assemblycache `ProvideAssembly`, und klicken Sie dann die Anwendungsbasis, um einen Assemblyverweis aufzulösen Prüfpunkte.</span><span class="sxs-lookup"><span data-stu-id="e6370-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6370-133">Bei der Initialisierung die CLR ruft `GetNonHostStoreAssemblies` nur einmal.</span><span class="sxs-lookup"><span data-stu-id="e6370-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="e6370-134">Die Methode wird nicht erneut aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e6370-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6370-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6370-135">Requirements</span></span>  
 <span data-ttu-id="e6370-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6370-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6370-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6370-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6370-138">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e6370-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6370-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6370-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6370-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6370-140">See Also</span></span>  
 [<span data-ttu-id="e6370-141">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6370-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="e6370-142">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6370-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="e6370-143">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6370-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
