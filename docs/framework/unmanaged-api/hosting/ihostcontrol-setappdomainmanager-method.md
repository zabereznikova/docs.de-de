---
title: IHostControl::SetAppDomainManager-Methode
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: 2f4c004db39c14e7a71b0caa55a6089e8f69ca3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680655"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="99fe1-102">IHostControl::SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="99fe1-102">IHostControl::SetAppDomainManager Method</span></span>

<span data-ttu-id="99fe1-103">Benachrichtigt den Host, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="99fe1-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99fe1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99fe1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99fe1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99fe1-105">Parameters</span></span>  

 `dwAppDomainID`  
 <span data-ttu-id="99fe1-106">in Der numerische Bezeichner des ausgewählten <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="99fe1-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="99fe1-107">in Ein Zeiger auf das <xref:System.AppDomainManager> Objekt, das der Host als implementiert `IUnknown` .</span><span class="sxs-lookup"><span data-stu-id="99fe1-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99fe1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99fe1-108">Return Value</span></span>  
  
|<span data-ttu-id="99fe1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99fe1-109">HRESULT</span></span>|<span data-ttu-id="99fe1-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="99fe1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99fe1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="99fe1-111">S_OK</span></span>|<span data-ttu-id="99fe1-112">`SetAppDomainManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="99fe1-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="99fe1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99fe1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99fe1-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="99fe1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99fe1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99fe1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99fe1-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="99fe1-116">The call timed out.</span></span>|  
|<span data-ttu-id="99fe1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99fe1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99fe1-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="99fe1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99fe1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99fe1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99fe1-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="99fe1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99fe1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99fe1-121">E_FAIL</span></span>|<span data-ttu-id="99fe1-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="99fe1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99fe1-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="99fe1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99fe1-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="99fe1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99fe1-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99fe1-125">Remarks</span></span>  

 <span data-ttu-id="99fe1-126"><xref:System.AppDomainManager>Stellt einen Mechanismus bereit, mit dem ein Bootstrap in verwalteten Code durchgeführt und die Erstellung und die Einstellungen der einzelnen Steuerelemente gesteuert werden können <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="99fe1-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="99fe1-127"><xref:System.AppDomainManager>Wird in jedes <xref:System.AppDomain> erstellt, wenn das <xref:System.AppDomain> erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="99fe1-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="99fe1-128">Wenn dies der Fall ist, benachrichtigt die CLR den Host, dass die Anwendungsdomäne erstellt wurde, indem der Wert des-Parameters festgelegt wird `pUnkAppDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="99fe1-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="99fe1-129">In der Implementierung der- `SetAppDomainManager` Methode kann der Host den Assemblynamen und den Typ für den Anwendungs Domänen-Manager festlegen.</span><span class="sxs-lookup"><span data-stu-id="99fe1-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99fe1-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="99fe1-130">Requirements</span></span>  

 <span data-ttu-id="99fe1-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99fe1-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99fe1-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="99fe1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99fe1-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99fe1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99fe1-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99fe1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99fe1-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99fe1-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="99fe1-136">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99fe1-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
