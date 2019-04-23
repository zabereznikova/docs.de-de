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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160e31859e3d58812861d4462e77d68fa18d6186
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079655"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="9fe03-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets-Methode</span><span class="sxs-lookup"><span data-stu-id="9fe03-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="9fe03-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9fe03-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe03-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fe03-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9fe03-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9fe03-105">Return Value</span></span>  
  
|<span data-ttu-id="9fe03-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fe03-106">HRESULT</span></span>|<span data-ttu-id="9fe03-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fe03-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fe03-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fe03-108">S_OK</span></span>|<span data-ttu-id="9fe03-109">`SetEagerSerializeGrantSets` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9fe03-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="9fe03-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9fe03-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9fe03-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9fe03-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9fe03-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9fe03-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9fe03-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9fe03-113">The call timed out.</span></span>|  
|<span data-ttu-id="9fe03-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9fe03-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9fe03-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9fe03-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9fe03-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9fe03-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9fe03-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9fe03-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9fe03-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9fe03-118">E_FAIL</span></span>|<span data-ttu-id="9fe03-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9fe03-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9fe03-120">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fe03-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9fe03-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9fe03-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fe03-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fe03-122">Requirements</span></span>  
 <span data-ttu-id="9fe03-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fe03-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe03-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9fe03-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fe03-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9fe03-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fe03-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe03-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe03-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fe03-127">See also</span></span>

- [<span data-ttu-id="9fe03-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fe03-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9fe03-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fe03-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
