---
title: ICorConfiguration::SetGCThreadControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 28b012bbe3f8c11ecd0afb8b5905336bd99c349c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724025"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="4388e-102">ICorConfiguration::SetGCThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="4388e-102">ICorConfiguration::SetGCThreadControl Method</span></span>

<span data-ttu-id="4388e-103">Legt die Rückruf Schnittstelle für das Planen von Threads für nicht-Lauf Zeit Aufgaben fest, die andernfalls für eine Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="4388e-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4388e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4388e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4388e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4388e-105">Parameters</span></span>  

 `pGCThreadControl`  
 <span data-ttu-id="4388e-106">in Ein Zeiger auf ein [IGCThreadControl](igcthreadcontrol-interface.md) -Objekt, das den Host über die Unterbrechung von Threads für nicht-Lauf Zeit Aufgaben benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="4388e-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4388e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4388e-107">Remarks</span></span>  

 <span data-ttu-id="4388e-108">Der Host kann im [IGCThreadControl:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) -Rückruf auswählen, ob ein Thread neu geplant werden soll.</span><span class="sxs-lookup"><span data-stu-id="4388e-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4388e-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4388e-109">Requirements</span></span>  

 <span data-ttu-id="4388e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4388e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4388e-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4388e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4388e-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4388e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4388e-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4388e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4388e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4388e-114">See also</span></span>

- [<span data-ttu-id="4388e-115">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4388e-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
