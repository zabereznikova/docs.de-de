---
title: ICLRControl::SetAppDomainManagerType-Methode
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: e62f9fd6b8421ea131eff0e6b36523718589c921
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615825"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="388d9-102">ICLRControl::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="388d9-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="388d9-103">Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungs Domänen-Manager fest.</span><span class="sxs-lookup"><span data-stu-id="388d9-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="388d9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="388d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="388d9-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="388d9-106">in Der Name der Assembly, in der der von abgeleitete Typ <xref:System.AppDomainManager> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="388d9-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="388d9-107">in Der Name des Typs, der im- `pwzAppDomainManagerAssembly` Parameter implementiert ist, der die Funktionen von implementiert <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="388d9-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="388d9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="388d9-108">Return Value</span></span>  
  
|<span data-ttu-id="388d9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="388d9-109">HRESULT</span></span>|<span data-ttu-id="388d9-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="388d9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="388d9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="388d9-111">S_OK</span></span>|<span data-ttu-id="388d9-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="388d9-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="388d9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="388d9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="388d9-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="388d9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="388d9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="388d9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="388d9-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="388d9-116">The call timed out.</span></span>|  
|<span data-ttu-id="388d9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="388d9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="388d9-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="388d9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="388d9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="388d9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="388d9-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="388d9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="388d9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="388d9-121">E_FAIL</span></span>|<span data-ttu-id="388d9-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="388d9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="388d9-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="388d9-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="388d9-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="388d9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="388d9-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="388d9-125">Requirements</span></span>  
 <span data-ttu-id="388d9-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="388d9-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388d9-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="388d9-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="388d9-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="388d9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="388d9-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="388d9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388d9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="388d9-130">See also</span></span>

- [<span data-ttu-id="388d9-131">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="388d9-131">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="388d9-132">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="388d9-132">IHostControl Interface</span></span>](ihostcontrol-interface.md)
