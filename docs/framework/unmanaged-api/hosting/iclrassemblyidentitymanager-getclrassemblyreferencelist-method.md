---
title: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49962e632ced9aac376791ead672e6910117ee10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434738"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="55ef2-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList-Methode</span><span class="sxs-lookup"><span data-stu-id="55ef2-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="55ef2-103">Ruft einen Schnittstellenzeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Instanz aus der angegebenen Liste von partiellen Assemblyidentitäten.</span><span class="sxs-lookup"><span data-stu-id="55ef2-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ef2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55ef2-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55ef2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55ef2-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="55ef2-106">[in] Ein Array von Null endende Zeichenfolgen im Format "name-Eigenschaft = Wert...", die eine Liste der partiellen Assemblyidentitäten angeben.</span><span class="sxs-lookup"><span data-stu-id="55ef2-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="55ef2-107">[in] Die Anzahl der Elemente im `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="55ef2-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="55ef2-108">[out] Einen Schnittstellenzeiger auf eine `ICLRAssemblyReferenceList` Objekt, das für die Liste der Assemblys, die im angegebenen Assemblyidentitätsdaten enthält `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="55ef2-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55ef2-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="55ef2-109">Return Value</span></span>  
  
|<span data-ttu-id="55ef2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55ef2-110">HRESULT</span></span>|<span data-ttu-id="55ef2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55ef2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55ef2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="55ef2-112">S_OK</span></span>|<span data-ttu-id="55ef2-113">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="55ef2-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="55ef2-114">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="55ef2-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55ef2-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="55ef2-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55ef2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55ef2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55ef2-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="55ef2-117">The call timed out.</span></span>|  
|<span data-ttu-id="55ef2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55ef2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55ef2-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="55ef2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55ef2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55ef2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55ef2-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="55ef2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55ef2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55ef2-122">E_FAIL</span></span>|<span data-ttu-id="55ef2-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="55ef2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55ef2-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="55ef2-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55ef2-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="55ef2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55ef2-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55ef2-126">Requirements</span></span>  
 <span data-ttu-id="55ef2-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55ef2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ef2-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55ef2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55ef2-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="55ef2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55ef2-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ef2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ef2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55ef2-131">See Also</span></span>  
 [<span data-ttu-id="55ef2-132">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55ef2-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="55ef2-133">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55ef2-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
