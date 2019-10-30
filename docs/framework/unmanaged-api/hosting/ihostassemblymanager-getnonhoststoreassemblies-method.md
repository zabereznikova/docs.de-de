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
ms.openlocfilehash: eb715e1a4f9a210a1440874a9a8cea2d85345d33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124578"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="ac410-102">IHostAssemblyManager::GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="ac410-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="ac410-103">Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host erwartet, dass die Common Language Runtime (CLR) geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ac410-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac410-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac410-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac410-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac410-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="ac410-106">vorgenommen Ein Zeiger auf die Adresse einer `ICLRAssemblyReferenceList`, die eine Liste der Verweise auf Assemblys enthält, die der Host erwartet, dass die CLR geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ac410-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac410-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac410-107">Return Value</span></span>  
  
|<span data-ttu-id="ac410-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac410-108">HRESULT</span></span>|<span data-ttu-id="ac410-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac410-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac410-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac410-110">S_OK</span></span>|<span data-ttu-id="ac410-111">`GetNonHostStoreAssemblies` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ac410-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="ac410-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac410-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac410-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ac410-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac410-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac410-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac410-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ac410-115">The call timed out.</span></span>|  
|<span data-ttu-id="ac410-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac410-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac410-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ac410-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac410-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac410-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac410-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ac410-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac410-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac410-120">E_FAIL</span></span>|<span data-ttu-id="ac410-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ac410-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac410-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac410-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac410-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ac410-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ac410-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ac410-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ac410-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für die angeforderte `ICLRAssemblyReferenceList`zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac410-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac410-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac410-126">Remarks</span></span>  
 <span data-ttu-id="ac410-127">Die CLR löst Verweise mithilfe der folgenden Richtlinien auf:</span><span class="sxs-lookup"><span data-stu-id="ac410-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="ac410-128">Zuerst wird die Liste der von `GetNonHostStoreAssemblies`zurückgegebenen Assemblyverweise konsultiert.</span><span class="sxs-lookup"><span data-stu-id="ac410-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="ac410-129">Wenn die Assembly in der Liste angezeigt wird, bindet die CLR Sie normal an Sie.</span><span class="sxs-lookup"><span data-stu-id="ac410-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="ac410-130">Wenn die Assembly nicht in der Liste angezeigt wird und der Host eine Implementierung von [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)bereitgestellt hat, ruft die CLR [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) auf, damit der Host die Assembly bereitstellen kann, an die die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="ac410-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="ac410-131">Andernfalls kann die CLR nicht an die Assembly gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="ac410-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="ac410-132">Wenn der Host `ppReferenceList` auf NULL festlegt, testet die CLR zuerst den globalen Assemblycache, ruft `ProvideAssembly`auf und testet dann die Anwendungs Basis, um einen Assemblyverweis aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="ac410-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac410-133">Bei der Initialisierung Ruft die CLR `GetNonHostStoreAssemblies` nur einmal auf.</span><span class="sxs-lookup"><span data-stu-id="ac410-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="ac410-134">Die Methode wird nicht erneut aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac410-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac410-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac410-135">Requirements</span></span>  
 <span data-ttu-id="ac410-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac410-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac410-137">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ac410-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac410-138">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ac410-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac410-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac410-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac410-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac410-140">See also</span></span>

- [<span data-ttu-id="ac410-141">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac410-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ac410-142">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac410-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="ac410-143">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac410-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
