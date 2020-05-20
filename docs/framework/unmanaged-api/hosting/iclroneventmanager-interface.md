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
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703517"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="27f13-102">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27f13-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="27f13-103">Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für Common Language Runtime (CLR)-Ereignisse zu registrieren und die Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="27f13-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27f13-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="27f13-104">Methods</span></span>  
  
|<span data-ttu-id="27f13-105">Methode</span><span class="sxs-lookup"><span data-stu-id="27f13-105">Method</span></span>|<span data-ttu-id="27f13-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27f13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27f13-107">RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="27f13-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="27f13-108">Registriert einen Rückruf Zeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="27f13-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="27f13-109">UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="27f13-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="27f13-110">Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="27f13-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27f13-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27f13-111">Remarks</span></span>  
 <span data-ttu-id="27f13-112">Um Ereignis Rückrufe zu registrieren und deren Registrierung aufzuheben, erhält der Host einen Verweis auf, `ICLROnEventManager` indem er die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="27f13-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27f13-113">Die von [EClrEvent](eclrevent-enumeration.md) beschriebenen Ereignisse können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="27f13-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27f13-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27f13-114">Requirements</span></span>  
 <span data-ttu-id="27f13-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27f13-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27f13-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="27f13-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27f13-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="27f13-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27f13-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27f13-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f13-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27f13-119">See also</span></span>

- [<span data-ttu-id="27f13-120">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="27f13-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="27f13-121">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27f13-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="27f13-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27f13-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="27f13-123">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="27f13-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
