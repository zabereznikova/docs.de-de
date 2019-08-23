---
title: IHostAssemblyManager::GetAssemblyStore-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62965fa928522052b6885769e02c0211ca8d3fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937937"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="8f59d-102">IHostAssemblyManager::GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="8f59d-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="8f59d-103">Ruft einen Schnittstellen Zeiger auf einen [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) ab, der die Liste der vom Host geladenen Assemblys darstellt.</span><span class="sxs-lookup"><span data-stu-id="8f59d-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f59d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f59d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f59d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f59d-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="8f59d-106">vorgenommen Ein Funktionszeiger auf eine `IHostAssemblyStore` -Instanz oder NULL, wenn der Host nicht implementiert. `IHostAssemblyStore`</span><span class="sxs-lookup"><span data-stu-id="8f59d-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f59d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f59d-107">Return Value</span></span>  
  
|<span data-ttu-id="8f59d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f59d-108">HRESULT</span></span>|<span data-ttu-id="8f59d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f59d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f59d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f59d-110">S_OK</span></span>|<span data-ttu-id="8f59d-111">`GetAssemblyStore`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f59d-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="8f59d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f59d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f59d-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8f59d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8f59d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f59d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f59d-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8f59d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8f59d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f59d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f59d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8f59d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f59d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f59d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f59d-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8f59d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f59d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f59d-120">E_FAIL</span></span>|<span data-ttu-id="8f59d-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8f59d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f59d-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f59d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f59d-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8f59d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8f59d-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="8f59d-124">E_NOINTERFACE</span></span>|<span data-ttu-id="8f59d-125">Der Host stellt keine Implementierung von `IHostAssemblyStore`bereit.</span><span class="sxs-lookup"><span data-stu-id="8f59d-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f59d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f59d-126">Remarks</span></span>  
 <span data-ttu-id="8f59d-127">`IHostAssemblyStore`stellt Methoden bereit, mit denen ein Host unabhängig von der CLR an Assemblys und Module gebunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f59d-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="8f59d-128">Hosts stellen in der Regel Assemblyspeicher bereit, damit Assemblys aus anderen Formaten als dem Dateisystem geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="8f59d-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f59d-129">Wenn der Host nicht implementiert `IHostAssemblyStore`, `GetAssemblyStore` muss einen HRESULT-Wert von E_NOINTERFACE zurückgeben und sollte auf `ppAssemblyStore` NULL festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8f59d-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f59d-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f59d-130">Requirements</span></span>  
 <span data-ttu-id="8f59d-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f59d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f59d-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f59d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f59d-133">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f59d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f59d-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f59d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f59d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f59d-135">See also</span></span>

- [<span data-ttu-id="8f59d-136">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f59d-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="8f59d-137">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f59d-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
