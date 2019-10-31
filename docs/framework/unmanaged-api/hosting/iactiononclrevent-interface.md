---
title: IActionOnCLREvent-Schnittstelle
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 9277fe2c241ce4f502339de826dccd08a2ce8055
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126955"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="1b14b-102">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b14b-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="1b14b-103">Stellt die [iaktiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) -Methode bereit, die Rückrufe für Ereignisse ausführt, die mit einem Aufruf der [ICLROnEventManager:: registeraktiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) -Methode registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="1b14b-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b14b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1b14b-104">Methods</span></span>  
  
|<span data-ttu-id="1b14b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1b14b-105">Method</span></span>|<span data-ttu-id="1b14b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b14b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b14b-107">OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="1b14b-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="1b14b-108">Führt einen Rückruf für ein registriertes Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="1b14b-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b14b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b14b-109">Requirements</span></span>  
 <span data-ttu-id="1b14b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b14b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b14b-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1b14b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b14b-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1b14b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b14b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b14b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b14b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b14b-114">See also</span></span>

- [<span data-ttu-id="1b14b-115">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b14b-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="1b14b-116">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b14b-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1b14b-117">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b14b-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="1b14b-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b14b-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
