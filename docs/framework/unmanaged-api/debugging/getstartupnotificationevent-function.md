---
title: GetStartupNotificationEvent-Funktion
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: 1c6ad35cd42760a4d88cf78bb084a25cf58a1064
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676087"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="2bf84-102">GetStartupNotificationEvent-Funktion</span><span class="sxs-lookup"><span data-stu-id="2bf84-102">GetStartupNotificationEvent Function</span></span>

<span data-ttu-id="2bf84-103">Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="2bf84-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bf84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bf84-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bf84-105">Parameters</span></span>  

 `debuggeePID`  
 <span data-ttu-id="2bf84-106">[in] Prozessbezeichner des Zielprozesses, von dem CLR-Startbenachrichtigungen empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="2bf84-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="2bf84-107">[out] Ein Zeiger auf ein Handle, das von einer CRL beim Start signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2bf84-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bf84-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2bf84-108">Return Value</span></span>  

 <span data-ttu-id="2bf84-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bf84-109">S_OK</span></span>  
 <span data-ttu-id="2bf84-110">Das Handle für das Start-Benachrichtigungsereignis wurde wurde erfolgreich empfangen.</span><span class="sxs-lookup"><span data-stu-id="2bf84-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="2bf84-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2bf84-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="2bf84-112">`phStartupEvent` ist Null oder `debuggeePID` bezieht sich nicht auf einen Prozess, der derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2bf84-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="2bf84-113">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="2bf84-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2bf84-114">Das Handle zum Start-Benachrichtigungsereignis konnte nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2bf84-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bf84-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2bf84-115">Remarks</span></span>  

 <span data-ttu-id="2bf84-116">Unter dem Windows-Betriebssystem wird `debuggeePID` einem Betriebssystem-Prozessbezeichner zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2bf84-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="2bf84-117">Das Ereignis wird signalisiert, bevor irgendwelcher verwalteter Code von der CLR ausgeführt wurde, die das Ereignis signalisiert hat.</span><span class="sxs-lookup"><span data-stu-id="2bf84-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf84-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2bf84-118">Requirements</span></span>  

 <span data-ttu-id="2bf84-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bf84-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf84-120">**Header:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="2bf84-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="2bf84-121">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="2bf84-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="2bf84-122">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2bf84-122">**.NET Framework Versions:** 3.5 SP1</span></span>
