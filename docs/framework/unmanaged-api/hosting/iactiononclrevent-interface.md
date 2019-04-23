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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864a8a4dd9f96da2fd0e0025848a910b4f8b0a70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180510"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="665d0-102">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="665d0-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="665d0-103">Stellt die [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) Methode, die Rückrufe für Ereignisse ausführt, die mit einem Aufruf von registriert wurden die [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="665d0-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="665d0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="665d0-104">Methods</span></span>  
  
|<span data-ttu-id="665d0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="665d0-105">Method</span></span>|<span data-ttu-id="665d0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="665d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="665d0-107">OnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="665d0-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="665d0-108">Führt einen Rückruf für ein registriertes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="665d0-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="665d0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="665d0-109">Requirements</span></span>  
 <span data-ttu-id="665d0-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="665d0-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="665d0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="665d0-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="665d0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="665d0-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="665d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665d0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="665d0-114">See also</span></span>

- [<span data-ttu-id="665d0-115">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="665d0-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="665d0-116">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="665d0-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="665d0-117">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="665d0-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="665d0-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="665d0-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
