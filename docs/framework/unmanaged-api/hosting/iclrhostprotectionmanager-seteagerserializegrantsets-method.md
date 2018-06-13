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
ms.openlocfilehash: e9bddaa25ba83570389a9d70ac1a9f60357f533c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432221"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="8dee6-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets-Methode</span><span class="sxs-lookup"><span data-stu-id="8dee6-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="8dee6-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8dee6-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dee6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8dee6-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8dee6-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8dee6-105">Return Value</span></span>  
  
|<span data-ttu-id="8dee6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8dee6-106">HRESULT</span></span>|<span data-ttu-id="8dee6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dee6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8dee6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8dee6-108">S_OK</span></span>|<span data-ttu-id="8dee6-109">`SetEagerSerializeGrantSets` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8dee6-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="8dee6-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="8dee6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8dee6-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8dee6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8dee6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8dee6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8dee6-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8dee6-113">The call timed out.</span></span>|  
|<span data-ttu-id="8dee6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8dee6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8dee6-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8dee6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8dee6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8dee6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8dee6-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8dee6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8dee6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8dee6-118">E_FAIL</span></span>|<span data-ttu-id="8dee6-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8dee6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8dee6-120">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="8dee6-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8dee6-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8dee6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8dee6-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8dee6-122">Requirements</span></span>  
 <span data-ttu-id="8dee6-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dee6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dee6-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8dee6-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8dee6-125">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8dee6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dee6-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dee6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dee6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dee6-127">See Also</span></span>  
 [<span data-ttu-id="8dee6-128">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8dee6-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8dee6-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8dee6-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
