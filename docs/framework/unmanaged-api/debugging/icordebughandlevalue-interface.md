---
title: ICorDebugHandleValue Schnittstelle1
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
ms.openlocfilehash: ed6ba8a738b4086b9150e0a1c7b300a519fa3092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419106"
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="0ed98-102">ICorDebugHandleValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="0ed98-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="0ed98-103">Eine Unterklasse von ICorDebugReferenceValue, die einen Verweiswert darstellt, zu dem der Debugger einen Handle zur Garbagecollection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="0ed98-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ed98-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0ed98-104">Methods</span></span>  
  
|<span data-ttu-id="0ed98-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0ed98-105">Method</span></span>|<span data-ttu-id="0ed98-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ed98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ed98-107">Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="0ed98-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="0ed98-108">Gibt das Handle verweist diese frei `ICorDebugHandleValue` Objekt nicht explizit freigegeben den Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="0ed98-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="0ed98-109">GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="0ed98-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="0ed98-110">Ruft einen CorDebugHandleType-Wert, der die Art der verwiesen, die von diesem Handle beschreibt `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="0ed98-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ed98-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ed98-111">Remarks</span></span>  
 <span data-ttu-id="0ed98-112">Ein `ICorDebugReferenceValue` Objekt wird durch eine Unterbrechung der Ausführung des gedebuggten Codes für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="0ed98-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="0ed98-113">Ein `ICorDebugHandleValue` verwaltet seinen Verweis durch Zeilenumbrüche und Fortsetzungen sein, bis sie explizit freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0ed98-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed98-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0ed98-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ed98-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ed98-115">Requirements</span></span>  
 <span data-ttu-id="0ed98-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ed98-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ed98-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ed98-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ed98-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ed98-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ed98-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ed98-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed98-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ed98-120">See Also</span></span>  
 [<span data-ttu-id="0ed98-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0ed98-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
