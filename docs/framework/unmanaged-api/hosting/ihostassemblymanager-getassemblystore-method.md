---
title: IHostAssemblyManager::GetAssemblyStore-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d838ee8383a4e11f5d43c4a3751c4a90503906fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="4ded1-102">IHostAssemblyManager::GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="4ded1-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="4ded1-103">Ruft einen Schnittstellenzeiger auf eine [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , die die Liste der Assemblys, die vom Host geladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="4ded1-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ded1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ded1-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ded1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ded1-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="4ded1-106">[out] Ein Funktionszeiger auf eine `IHostAssemblyStore` -Instanz oder null, wenn der Host keine implementiert `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="4ded1-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ded1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ded1-107">Return Value</span></span>  
  
|<span data-ttu-id="4ded1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ded1-108">HRESULT</span></span>|<span data-ttu-id="4ded1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ded1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ded1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ded1-110">S_OK</span></span>|<span data-ttu-id="4ded1-111">`GetAssemblyStore`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4ded1-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="4ded1-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="4ded1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ded1-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4ded1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ded1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ded1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ded1-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4ded1-115">The call timed out.</span></span>|  
|<span data-ttu-id="4ded1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ded1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ded1-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4ded1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ded1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ded1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ded1-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="4ded1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ded1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ded1-120">E_FAIL</span></span>|<span data-ttu-id="4ded1-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4ded1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ded1-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="4ded1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ded1-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4ded1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4ded1-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="4ded1-124">E_NOINTERFACE</span></span>|<span data-ttu-id="4ded1-125">Der Host bietet keine Implementierung von `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="4ded1-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ded1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ded1-126">Remarks</span></span>  
 <span data-ttu-id="4ded1-127">`IHostAssemblyStore`enthält Methoden, die einen Host zum Binden an die Assemblys und Modulen unabhängig von der CLR zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4ded1-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="4ded1-128">Hosts stellen normalerweise Assembly speichert damit Assemblys von anderen Formaten als dem Dateisystem geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="4ded1-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ded1-129">Wenn der Host keine implementiert `IHostAssemblyStore`, `GetAssemblyStore` E_NOINTERFACE HRESULT-Wert zurückgeben und darf festgelegt `ppAssemblyStore` auf Null.</span><span class="sxs-lookup"><span data-stu-id="4ded1-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ded1-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ded1-130">Requirements</span></span>  
 <span data-ttu-id="4ded1-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ded1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ded1-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ded1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ded1-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4ded1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ded1-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ded1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ded1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ded1-135">See Also</span></span>  
 [<span data-ttu-id="4ded1-136">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ded1-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="4ded1-137">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ded1-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
