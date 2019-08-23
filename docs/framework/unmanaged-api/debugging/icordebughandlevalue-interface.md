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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3219554cf953b8de31e236b2f484478172673f7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915007"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="bea4a-102">ICorDebugHandleValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bea4a-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="bea4a-103">Eine Unterklasse von ICorDebugReferenceValue, die einen Verweis Wert darstellt, mit dem der Debugger ein Handle für Garbage Collection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="bea4a-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bea4a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bea4a-104">Methods</span></span>  
  
|<span data-ttu-id="bea4a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bea4a-105">Method</span></span>|<span data-ttu-id="bea4a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bea4a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bea4a-107">Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="bea4a-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="bea4a-108">Gibt das Handle frei, auf `ICorDebugHandleValue` das dieses-Objekt verweist, ohne den Schnittstellen Zeiger explizit freizugeben.</span><span class="sxs-lookup"><span data-stu-id="bea4a-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="bea4a-109">GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="bea4a-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="bea4a-110">Ruft einen CorDebugHandleType-Wert ab, der die Art des Handles beschreibt `ICorDebugHandleValue`, auf den von diesem verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bea4a-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bea4a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bea4a-111">Remarks</span></span>  
 <span data-ttu-id="bea4a-112">Ein `ICorDebugReferenceValue` Objekt wird durch einen Umbruch bei der Ausführung des decodierten Codes ungültig.</span><span class="sxs-lookup"><span data-stu-id="bea4a-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="bea4a-113">Ein `ICorDebugHandleValue` behält seinen Verweis durch Unterbrechungen und Fortsetzungen bei, bis er explizit freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bea4a-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bea4a-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bea4a-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bea4a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bea4a-115">Requirements</span></span>  
 <span data-ttu-id="bea4a-116">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bea4a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea4a-117">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="bea4a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bea4a-118">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bea4a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bea4a-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea4a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea4a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bea4a-120">See also</span></span>

- [<span data-ttu-id="bea4a-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bea4a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
