---
title: ICorDebugHandleValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: e695a93036e00e651ecababb0e1407661bcc48d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729082"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="6f0f1-102">ICorDebugHandleValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f0f1-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="6f0f1-103">Eine Unterklasse von ICorDebugReferenceValue, die einen Verweis Wert darstellt, mit dem der Debugger ein Handle für Garbage Collection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="6f0f1-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f0f1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6f0f1-104">Methods</span></span>  
  
|<span data-ttu-id="6f0f1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6f0f1-105">Method</span></span>|<span data-ttu-id="6f0f1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f0f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f0f1-107">Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="6f0f1-107">Dispose Method</span></span>](icordebughandlevalue-dispose-method.md)|<span data-ttu-id="6f0f1-108">Gibt das Handle frei, auf das dieses-Objekt verweist, `ICorDebugHandleValue` ohne den Schnittstellen Zeiger explizit freizugeben.</span><span class="sxs-lookup"><span data-stu-id="6f0f1-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="6f0f1-109">GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="6f0f1-109">GetHandleType Method</span></span>](icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="6f0f1-110">Ruft einen CorDebugHandleType-Wert ab, der die Art des Handles beschreibt, auf den von diesem verwiesen wird `ICorDebugHandleValue` .</span><span class="sxs-lookup"><span data-stu-id="6f0f1-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f0f1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f0f1-111">Remarks</span></span>  

 <span data-ttu-id="6f0f1-112">Ein `ICorDebugReferenceValue` Objekt wird durch einen Umbruch bei der Ausführung des decodierten Codes ungültig.</span><span class="sxs-lookup"><span data-stu-id="6f0f1-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="6f0f1-113">Ein `ICorDebugHandleValue` behält seinen Verweis durch Unterbrechungen und Fortsetzungen bei, bis er explizit freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6f0f1-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f0f1-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6f0f1-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f0f1-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f0f1-115">Requirements</span></span>  

 <span data-ttu-id="6f0f1-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f0f1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f0f1-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f0f1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f0f1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f0f1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f0f1-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f0f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0f1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f0f1-120">See also</span></span>

- [<span data-ttu-id="6f0f1-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f0f1-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
