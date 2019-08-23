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
ms.openlocfilehash: 3633db69877db771d919c9f43da4809f8321f77c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951203"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="0cdae-102">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdae-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="0cdae-103">Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für Common Language Runtime (CLR)-Ereignisse zu registrieren und die Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="0cdae-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cdae-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0cdae-104">Methods</span></span>  
  
|<span data-ttu-id="0cdae-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0cdae-105">Method</span></span>|<span data-ttu-id="0cdae-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0cdae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cdae-107">RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0cdae-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="0cdae-108">Registriert einen Rückruf Zeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0cdae-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="0cdae-109">UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="0cdae-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="0cdae-110">Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="0cdae-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cdae-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cdae-111">Remarks</span></span>  
 <span data-ttu-id="0cdae-112">Um Ereignis Rückrufe zu registrieren und deren Registrierung aufzuheben, erhält der Host einen `ICLROnEventManager` Verweis auf, indem er die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0cdae-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cdae-113">Die von [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) beschriebenen Ereignisse können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="0cdae-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cdae-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cdae-114">Requirements</span></span>  
 <span data-ttu-id="0cdae-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cdae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cdae-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0cdae-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cdae-117">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0cdae-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cdae-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cdae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cdae-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cdae-119">See also</span></span>

- [<span data-ttu-id="0cdae-120">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0cdae-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="0cdae-121">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdae-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="0cdae-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cdae-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0cdae-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0cdae-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
