---
title: ICorDebugValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 7d3c35ed6cda637e3b885afe089ddfa590d51076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683601"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="85511-102">ICorDebugValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85511-102">ICorDebugValue Interface</span></span>

<span data-ttu-id="85511-103">Stellt einen Wert in dem Prozess dar, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="85511-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="85511-104">Der Wert kann ein Lese-oder ein Schreib Wert sein.</span><span class="sxs-lookup"><span data-stu-id="85511-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85511-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="85511-105">Methods</span></span>  
  
|<span data-ttu-id="85511-106">Methode</span><span class="sxs-lookup"><span data-stu-id="85511-106">Method</span></span>|<span data-ttu-id="85511-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85511-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85511-108">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="85511-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="85511-109">Diese Methode ist derzeit nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="85511-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="85511-110">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="85511-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="85511-111">Ruft die Adresse dieses- `ICorDebugValue` Objekts ab, das gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="85511-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="85511-112">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="85511-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="85511-113">Ruft die Größe des-Objekts in Bytes ab `ICorDebugValue` .</span><span class="sxs-lookup"><span data-stu-id="85511-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="85511-114">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="85511-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="85511-115">Ruft den primitiven Typ dieses- `ICorDebugValue` Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="85511-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85511-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85511-116">Remarks</span></span>  

 <span data-ttu-id="85511-117">Im Allgemeinen wird der Besitz eines Wert Objekts bei der Rückgabe übermittelt.</span><span class="sxs-lookup"><span data-stu-id="85511-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="85511-118">Der Empfänger ist dafür verantwortlich, einen Verweis aus dem-Objekt zu entfernen, wenn er mit dem-Objekt fertig ist.</span><span class="sxs-lookup"><span data-stu-id="85511-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="85511-119">Abhängig davon, wo der Wert aus abgerufen wurde, bleibt der Wert möglicherweise nicht gültig, nachdem der Prozess fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="85511-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="85511-120">Im Allgemeinen sollte der Wert nicht über einen Aufrufen der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode hinweg aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="85511-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85511-121">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="85511-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85511-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="85511-122">Requirements</span></span>  

 <span data-ttu-id="85511-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85511-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85511-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85511-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85511-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85511-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85511-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85511-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85511-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85511-127">See also</span></span>

- [<span data-ttu-id="85511-128">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85511-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="85511-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="85511-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
