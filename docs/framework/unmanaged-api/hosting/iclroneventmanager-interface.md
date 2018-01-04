---
title: ICLROnEventManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager
helpviewer_keywords: ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a19a3daf72cdfa493b09fa984fe7b50865ed30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="b36d0-102">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b36d0-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="b36d0-103">Enthält Methoden, die es dem Host zu registrieren und Aufheben der Rückrufe für common Language Runtime (CLR) Ereignisse ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b36d0-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b36d0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b36d0-104">Methods</span></span>  
  
|<span data-ttu-id="b36d0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b36d0-105">Method</span></span>|<span data-ttu-id="b36d0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b36d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b36d0-107">RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="b36d0-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="b36d0-108">Registriert einen Rückrufzeiger für das angegebene Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="b36d0-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="b36d0-109">UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="b36d0-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="b36d0-110">Hebt die Registrierung eines zuvor registrierten Rückrufzeigers für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b36d0-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b36d0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b36d0-111">Remarks</span></span>  
 <span data-ttu-id="b36d0-112">Zum Registrieren und Aufheben der Registrierung Ereignisrückrufe, ruft der Host einen Verweis auf `ICLROnEventManager` durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b36d0-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b36d0-113">Die Ereignisse, die durch beschrieben [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) kann ausgelöst werden, mehr als einmal und von anderen Threads um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="b36d0-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b36d0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b36d0-114">Requirements</span></span>  
 <span data-ttu-id="b36d0-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b36d0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b36d0-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b36d0-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b36d0-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b36d0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b36d0-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b36d0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b36d0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b36d0-119">See Also</span></span>  
 [<span data-ttu-id="b36d0-120">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b36d0-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="b36d0-121">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b36d0-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="b36d0-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b36d0-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="b36d0-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b36d0-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
