---
title: ICLRHostProtectionManager::SetEagerSerializeGrantSets-Methode
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
ms.openlocfilehash: be59acea8eadb0da9e3cd26cf17eb9e1617c3575
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141059"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="61af2-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets-Methode</span><span class="sxs-lookup"><span data-stu-id="61af2-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="61af2-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="61af2-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61af2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61af2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="61af2-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61af2-105">Return Value</span></span>  
  
|<span data-ttu-id="61af2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61af2-106">HRESULT</span></span>|<span data-ttu-id="61af2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61af2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61af2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="61af2-108">S_OK</span></span>|<span data-ttu-id="61af2-109">`SetEagerSerializeGrantSets` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="61af2-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="61af2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61af2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61af2-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="61af2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="61af2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61af2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61af2-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="61af2-113">The call timed out.</span></span>|  
|<span data-ttu-id="61af2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61af2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61af2-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="61af2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61af2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61af2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61af2-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="61af2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61af2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61af2-118">E_FAIL</span></span>|<span data-ttu-id="61af2-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="61af2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61af2-120">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61af2-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61af2-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="61af2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61af2-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61af2-122">Requirements</span></span>  
 <span data-ttu-id="61af2-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61af2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61af2-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="61af2-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61af2-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="61af2-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61af2-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61af2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61af2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61af2-127">See also</span></span>

- [<span data-ttu-id="61af2-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61af2-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="61af2-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61af2-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
