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
ms.openlocfilehash: 3377dcd5d45ca8e31a57a75bd81366d41837c12c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860713"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="99468-102">GetStartupNotificationEvent-Funktion</span><span class="sxs-lookup"><span data-stu-id="99468-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="99468-103">Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="99468-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99468-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99468-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="99468-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99468-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="99468-106">[in] Prozessbezeichner des Zielprozesses, von dem CLR-Startbenachrichtigungen empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="99468-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="99468-107">[out] Ein Zeiger auf ein Handle, das von einer CRL beim Start signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="99468-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99468-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99468-108">Return Value</span></span>  
 <span data-ttu-id="99468-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="99468-109">S_OK</span></span>  
 <span data-ttu-id="99468-110">Das Handle für das Start-Benachrichtigungsereignis wurde wurde erfolgreich empfangen.</span><span class="sxs-lookup"><span data-stu-id="99468-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="99468-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="99468-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="99468-112">`phStartupEvent` ist Null oder `debuggeePID` bezieht sich nicht auf einen Prozess, der derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99468-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="99468-113">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="99468-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="99468-114">Das Handle zum Start-Benachrichtigungsereignis konnte nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="99468-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99468-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99468-115">Remarks</span></span>  
 <span data-ttu-id="99468-116">Unter dem Windows-Betriebssystem wird `debuggeePID` einem Betriebssystem-Prozessbezeichner zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="99468-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="99468-117">Das Ereignis wird signalisiert, bevor irgendwelcher verwalteter Code von der CLR ausgeführt wurde, die das Ereignis signalisiert hat.</span><span class="sxs-lookup"><span data-stu-id="99468-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99468-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99468-118">Requirements</span></span>  
 <span data-ttu-id="99468-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99468-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99468-120">**Header:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="99468-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="99468-121">**Bibliothek:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="99468-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="99468-122">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="99468-122">**.NET Framework Versions:** 3.5 SP1</span></span>
