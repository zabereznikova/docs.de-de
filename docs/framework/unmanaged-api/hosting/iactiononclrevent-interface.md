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
ms.openlocfilehash: 4e72cd8bee2cb4f35155d7b99cfe8d9cf63f463a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616072"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="de0ce-102">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de0ce-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="de0ce-103">Stellt die [iaktiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) -Methode bereit, die Rückrufe für Ereignisse ausführt, die mit einem Aufruf der [ICLROnEventManager:: registeraktiononevent](iclroneventmanager-registeractiononevent-method.md) -Methode registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="de0ce-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de0ce-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="de0ce-104">Methods</span></span>  
  
|<span data-ttu-id="de0ce-105">Methode</span><span class="sxs-lookup"><span data-stu-id="de0ce-105">Method</span></span>|<span data-ttu-id="de0ce-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="de0ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de0ce-107">OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="de0ce-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="de0ce-108">Führt einen Rückruf für ein registriertes Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="de0ce-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de0ce-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de0ce-109">Requirements</span></span>  
 <span data-ttu-id="de0ce-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de0ce-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de0ce-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="de0ce-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de0ce-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="de0ce-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de0ce-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de0ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de0ce-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de0ce-114">See also</span></span>

- [<span data-ttu-id="de0ce-115">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="de0ce-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="de0ce-116">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de0ce-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="de0ce-117">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de0ce-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="de0ce-118">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="de0ce-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
