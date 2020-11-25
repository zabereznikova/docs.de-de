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
ms.openlocfilehash: 1948075d87b5a44397a1eaab3adb4edbc96d7143
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725631"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="415bb-102">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="415bb-102">ICLROnEventManager Interface</span></span>

<span data-ttu-id="415bb-103">Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für Common Language Runtime (CLR)-Ereignisse zu registrieren und die Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="415bb-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="415bb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="415bb-104">Methods</span></span>  
  
|<span data-ttu-id="415bb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="415bb-105">Method</span></span>|<span data-ttu-id="415bb-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="415bb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="415bb-107">RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="415bb-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="415bb-108">Registriert einen Rückruf Zeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="415bb-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="415bb-109">UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="415bb-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="415bb-110">Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="415bb-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="415bb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="415bb-111">Remarks</span></span>  

 <span data-ttu-id="415bb-112">Um Ereignis Rückrufe zu registrieren und deren Registrierung aufzuheben, erhält der Host einen Verweis auf, `ICLROnEventManager` indem er die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="415bb-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="415bb-113">Die von [EClrEvent](eclrevent-enumeration.md) beschriebenen Ereignisse können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="415bb-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="415bb-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="415bb-114">Requirements</span></span>  

 <span data-ttu-id="415bb-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="415bb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="415bb-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="415bb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="415bb-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="415bb-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="415bb-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="415bb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415bb-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="415bb-119">See also</span></span>

- [<span data-ttu-id="415bb-120">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="415bb-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="415bb-121">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="415bb-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="415bb-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="415bb-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="415bb-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="415bb-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
