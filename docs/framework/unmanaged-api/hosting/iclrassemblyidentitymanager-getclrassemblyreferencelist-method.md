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
ms.openlocfilehash: 7f09cb2264b21fdfbc892069f2c2f0a963b131f8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615968"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="9c17f-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList-Methode</span><span class="sxs-lookup"><span data-stu-id="9c17f-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="9c17f-103">Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) -Instanz aus der angegebenen Liste der partiellen Assemblyidentitäten ab.</span><span class="sxs-lookup"><span data-stu-id="9c17f-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c17f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c17f-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c17f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c17f-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="9c17f-106">in Ein Array von mit NULL endenden Zeichen folgen im Format "Name, Property = Value..." , die eine Liste von partiellen Assemblyidentitäten angeben.</span><span class="sxs-lookup"><span data-stu-id="9c17f-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="9c17f-107">in Die Anzahl der Elemente in `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="9c17f-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="9c17f-108">vorgenommen Ein Schnittstellen Zeiger auf ein- `ICLRAssemblyReferenceList` Objekt, das die Assemblyidentitätsdaten für die Liste der in angegebenen Assemblys enthält `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="9c17f-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c17f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9c17f-109">Return Value</span></span>  
  
|<span data-ttu-id="9c17f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c17f-110">HRESULT</span></span>|<span data-ttu-id="9c17f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c17f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c17f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c17f-112">S_OK</span></span>|<span data-ttu-id="9c17f-113">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9c17f-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="9c17f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c17f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c17f-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9c17f-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c17f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c17f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c17f-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9c17f-117">The call timed out.</span></span>|  
|<span data-ttu-id="9c17f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c17f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c17f-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9c17f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c17f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c17f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c17f-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9c17f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c17f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c17f-122">E_FAIL</span></span>|<span data-ttu-id="9c17f-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9c17f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c17f-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="9c17f-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c17f-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9c17f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c17f-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c17f-126">Requirements</span></span>  
 <span data-ttu-id="9c17f-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c17f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c17f-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9c17f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c17f-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9c17f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c17f-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c17f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c17f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c17f-131">See also</span></span>

- [<span data-ttu-id="9c17f-132">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c17f-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9c17f-133">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c17f-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
