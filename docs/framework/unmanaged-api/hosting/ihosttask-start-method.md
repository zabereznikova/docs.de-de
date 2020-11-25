---
title: IHostTask::Start-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: 4143c3d25dd5262a10b53708a249910cc79f5314
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720437"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="a0a4c-102">IHostTask::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="a0a4c-102">IHostTask::Start Method</span></span>

<span data-ttu-id="a0a4c-103">Fordert an, dass der Host die von der aktuellen [IHostTask](ihosttask-interface.md) -Instanz dargestellte Aufgabe von einem angehaltenen in einen livezustand verschiebt, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0a4c-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a0a4c-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0a4c-105">Return Value</span></span>  
  
|<span data-ttu-id="a0a4c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0a4c-106">HRESULT</span></span>|<span data-ttu-id="a0a4c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a0a4c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0a4c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0a4c-108">S_OK</span></span>|<span data-ttu-id="a0a4c-109">Der Start wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="a0a4c-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0a4c-110">E_FAIL</span></span>|<span data-ttu-id="a0a4c-111">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0a4c-112">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="a0a4c-113">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0a4c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0a4c-114">Remarks</span></span>  

 <span data-ttu-id="a0a4c-115">`Start` gibt immer den HRESULT-Wert S_OK zurück, außer in Fällen, in denen ein schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a0a4c-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a4c-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0a4c-116">Requirements</span></span>  

 <span data-ttu-id="a0a4c-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0a4c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a4c-118">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a0a4c-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0a4c-119">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a0a4c-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0a4c-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a4c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a4c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0a4c-121">See also</span></span>

- [<span data-ttu-id="a0a4c-122">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0a4c-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a0a4c-123">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0a4c-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a0a4c-124">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0a4c-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a0a4c-125">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0a4c-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
