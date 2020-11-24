---
title: ICorDebugValueBreakpoint-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: cf0a87afd1c0057c054205432fea7aa5844afb53
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684409"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="3c909-102">ICorDebugValueBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c909-102">ICorDebugValueBreakpoint Interface</span></span>

<span data-ttu-id="3c909-103">Erweitert die icordebubreakpoint-Schnittstelle, um Zugriff auf bestimmte Werte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3c909-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c909-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3c909-104">Methods</span></span>  
  
|<span data-ttu-id="3c909-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3c909-105">Method</span></span>|<span data-ttu-id="3c909-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3c909-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c909-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="3c909-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="3c909-108">Ruft einen Schnittstellen Zeiger auf ein icordebuvalue-Objekt ab, das den Wert des Objekts darstellt, für das der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3c909-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c909-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c909-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c909-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3c909-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c909-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3c909-111">Requirements</span></span>  

 <span data-ttu-id="3c909-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c909-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c909-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c909-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c909-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c909-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c909-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c909-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c909-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c909-116">See also</span></span>

- [<span data-ttu-id="3c909-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3c909-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
