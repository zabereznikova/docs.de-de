---
title: IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 750263f5620569ec1d51a4eebe7ea5d74bb84df2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650295"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="bb183-102">IHostAssemblyManager::GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="bb183-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="bb183-103">Ruft einen Schnittstellenzeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , das die Liste der Assemblys, die der Host erwartet, die common Language Runtime (CLR) beim Laden dass darstellt.</span><span class="sxs-lookup"><span data-stu-id="bb183-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb183-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb183-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb183-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb183-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="bb183-106">[out] Ein Zeiger auf die Adresse einer `ICLRAssemblyReferenceList` , enthält eine Liste der Verweise auf Assemblys, die der Host erwartet, dass die CLR geladen.</span><span class="sxs-lookup"><span data-stu-id="bb183-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb183-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb183-107">Return Value</span></span>  
  
|<span data-ttu-id="bb183-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb183-108">HRESULT</span></span>|<span data-ttu-id="bb183-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb183-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb183-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb183-110">S_OK</span></span>|<span data-ttu-id="bb183-111">`GetNonHostStoreAssemblies` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bb183-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="bb183-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bb183-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb183-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb183-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb183-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb183-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb183-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bb183-115">The call timed out.</span></span>|  
|<span data-ttu-id="bb183-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb183-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb183-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="bb183-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb183-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb183-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb183-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="bb183-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb183-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb183-120">E_FAIL</span></span>|<span data-ttu-id="bb183-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bb183-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb183-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb183-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb183-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="bb183-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bb183-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bb183-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bb183-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für die angeforderte erstellen `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="bb183-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb183-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb183-126">Remarks</span></span>  
 <span data-ttu-id="bb183-127">Die CLR löst Verweise, die mithilfe der folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="bb183-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="bb183-128">Zuerst herangezogen, die Liste von Assemblyverweisen, die vom `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="bb183-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="bb183-129">Wenn die Assembly in der Liste angezeigt wird, wird die CLR, die normalerweise gebunden.</span><span class="sxs-lookup"><span data-stu-id="bb183-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="bb183-130">Wenn die Assembly nicht in der Liste angezeigt, und der Host eine Implementierung von stellt [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), die CLR ruft [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) auf den Host ermöglichen die die Assembly zum Binden an.</span><span class="sxs-lookup"><span data-stu-id="bb183-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="bb183-131">Andernfalls kann die CLR auf die Assembly zu binden.</span><span class="sxs-lookup"><span data-stu-id="bb183-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="bb183-132">Wenn der Host setzt `ppReferenceList` Aufrufe im globalen Assemblycache, null, durchsucht die CLR zuerst `ProvideAssembly`, und von Tests, klicken Sie dann die Anwendungsbasis, um einen Assemblyverweis aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="bb183-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb183-133">Bei der Initialisierung, die CLR ruft `GetNonHostStoreAssemblies` nur einmal.</span><span class="sxs-lookup"><span data-stu-id="bb183-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="bb183-134">Die Methode wird nicht erneut aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bb183-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb183-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb183-135">Requirements</span></span>  
 <span data-ttu-id="bb183-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb183-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb183-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb183-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb183-138">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bb183-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb183-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb183-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb183-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb183-140">See also</span></span>

- [<span data-ttu-id="bb183-141">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb183-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="bb183-142">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb183-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="bb183-143">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb183-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
