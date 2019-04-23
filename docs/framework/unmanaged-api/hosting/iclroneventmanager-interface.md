---
title: ICLROnEventManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183000"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="d24eb-102">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d24eb-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="d24eb-103">Bietet Methoden, mit denen den Host zu registrieren und Aufheben der Registrierung von Rückrufen für common Language Runtime (CLR)-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d24eb-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d24eb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d24eb-104">Methods</span></span>  
  
|<span data-ttu-id="d24eb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d24eb-105">Method</span></span>|<span data-ttu-id="d24eb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d24eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d24eb-107">RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d24eb-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="d24eb-108">Registriert einen Rückrufzeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d24eb-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="d24eb-109">UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d24eb-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="d24eb-110">Hebt die Registrierung eines bereits registrierten Rückrufzeigers für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d24eb-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d24eb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d24eb-111">Remarks</span></span>  
 <span data-ttu-id="d24eb-112">Zum Registrieren und Aufheben der Registrierung Ereignisrückrufe, ruft der Host einen Verweis auf `ICLROnEventManager` durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d24eb-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d24eb-113">Die beschriebenen Ereignisse [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) kann ausgelöst werden, mehr als einmal und von verschiedenen Threads ein Entladen oder das Deaktivieren der CLR signalisiert.</span><span class="sxs-lookup"><span data-stu-id="d24eb-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d24eb-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d24eb-114">Requirements</span></span>  
 <span data-ttu-id="d24eb-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d24eb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d24eb-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d24eb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d24eb-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d24eb-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d24eb-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d24eb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24eb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d24eb-119">See also</span></span>

- [<span data-ttu-id="d24eb-120">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d24eb-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="d24eb-121">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d24eb-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="d24eb-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d24eb-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d24eb-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d24eb-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
