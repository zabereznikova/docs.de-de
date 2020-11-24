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
ms.openlocfilehash: 28fdd5340aee0fcd9875dd983c8c7649b5491c04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674709"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="deb26-102">ICLRControl::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="deb26-102">ICLRControl::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="deb26-103">Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungs Domänen-Manager fest.</span><span class="sxs-lookup"><span data-stu-id="deb26-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="deb26-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="deb26-105">Parameters</span></span>  

 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="deb26-106">in Der Name der Assembly, in der der von abgeleitete Typ <xref:System.AppDomainManager> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="deb26-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="deb26-107">in Der Name des Typs, der im- `pwzAppDomainManagerAssembly` Parameter implementiert ist, der die Funktionen von implementiert <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="deb26-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="deb26-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="deb26-108">Return Value</span></span>  
  
|<span data-ttu-id="deb26-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="deb26-109">HRESULT</span></span>|<span data-ttu-id="deb26-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="deb26-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="deb26-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="deb26-111">S_OK</span></span>|<span data-ttu-id="deb26-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="deb26-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="deb26-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="deb26-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="deb26-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="deb26-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="deb26-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="deb26-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="deb26-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="deb26-116">The call timed out.</span></span>|  
|<span data-ttu-id="deb26-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="deb26-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="deb26-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="deb26-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="deb26-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="deb26-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="deb26-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="deb26-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="deb26-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="deb26-121">E_FAIL</span></span>|<span data-ttu-id="deb26-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="deb26-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="deb26-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="deb26-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="deb26-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="deb26-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="deb26-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="deb26-125">Requirements</span></span>  

 <span data-ttu-id="deb26-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deb26-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb26-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="deb26-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="deb26-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="deb26-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="deb26-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb26-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb26-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="deb26-130">See also</span></span>

- [<span data-ttu-id="deb26-131">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="deb26-131">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="deb26-132">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="deb26-132">IHostControl Interface</span></span>](ihostcontrol-interface.md)
