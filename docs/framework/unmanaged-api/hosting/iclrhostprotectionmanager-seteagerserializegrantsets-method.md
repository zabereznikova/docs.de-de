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
ms.openlocfilehash: 948fd78ae2839bd24a44c8c0b806e32b1da7125f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729774"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="ba98f-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets-Methode</span><span class="sxs-lookup"><span data-stu-id="ba98f-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="ba98f-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ba98f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba98f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba98f-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ba98f-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba98f-105">Return Value</span></span>  
  
|<span data-ttu-id="ba98f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba98f-106">HRESULT</span></span>|<span data-ttu-id="ba98f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba98f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba98f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba98f-108">S_OK</span></span>|<span data-ttu-id="ba98f-109">`SetEagerSerializeGrantSets` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ba98f-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="ba98f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba98f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba98f-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ba98f-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba98f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba98f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba98f-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ba98f-113">The call timed out.</span></span>|  
|<span data-ttu-id="ba98f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba98f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba98f-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ba98f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba98f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba98f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba98f-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ba98f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba98f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba98f-118">E_FAIL</span></span>|<span data-ttu-id="ba98f-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ba98f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba98f-120">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba98f-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba98f-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ba98f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba98f-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba98f-122">Requirements</span></span>  
 <span data-ttu-id="ba98f-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba98f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba98f-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba98f-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba98f-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ba98f-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba98f-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba98f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba98f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba98f-127">See also</span></span>
- [<span data-ttu-id="ba98f-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba98f-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ba98f-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba98f-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
