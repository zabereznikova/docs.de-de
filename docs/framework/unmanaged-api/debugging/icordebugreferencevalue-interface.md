---
title: ICorDebugReferenceValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4709d1b8126436d4400c788891960100915cd1bc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971436"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="6c104-102">ICorDebugReferenceValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c104-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="6c104-103">Enthält Methoden, die einen Wert zu verwalten, der einen Verweis auf ein Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="6c104-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="6c104-104">(D. h. diese Schnittstelle stellt Methoden bereit, die einen Zeiger zu verwalten.) Diese Schnittstelle implementiert "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="6c104-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c104-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6c104-105">Methods</span></span>  
  
|<span data-ttu-id="6c104-106">Methode</span><span class="sxs-lookup"><span data-stu-id="6c104-106">Method</span></span>|<span data-ttu-id="6c104-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c104-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c104-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="6c104-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="6c104-109">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6c104-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="6c104-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="6c104-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="6c104-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="6c104-111">Not implemented.</span></span> <span data-ttu-id="6c104-112">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="6c104-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="6c104-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6c104-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="6c104-114">Ruft die aktuelle Speicheradresse des referenzierten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="6c104-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="6c104-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="6c104-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="6c104-116">Ruft einen Wert, der angibt, ob dies `ICorDebugReferenceValue` ein null-Wert in diesem Fall wird die `ICorDebugReferenceValue` verweist nicht auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="6c104-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="6c104-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6c104-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="6c104-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="6c104-118">Sets the current memory address.</span></span> <span data-ttu-id="6c104-119">D.h., diese Methode legt für diesen `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6c104-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c104-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c104-120">Remarks</span></span>  
 <span data-ttu-id="6c104-121">Die common Language Runtime (CLR) kann eine Garbagecollection für Objekte ausführen, wenn es sich bei der gedebuggte Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6c104-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="6c104-122">Die Garbagecollection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="6c104-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="6c104-123">Ein `ICorDebugReferenceValue` wird entweder zusammen mit der Garbagecollection, damit die Informationen nach der Garbagecollection aktualisiert, oder er wird implizit vor der Garbagecollection ungültig gemacht.</span><span class="sxs-lookup"><span data-stu-id="6c104-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="6c104-124">Die `ICorDebugReferenceValue` Objekt kann implizit ungültig werden, nachdem der gedebuggte Prozess fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="6c104-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="6c104-125">Der abgeleitete "ICorDebugHandleValue" ist nicht für ungültig erklärt, bis er explizit aufgehoben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="6c104-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c104-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6c104-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c104-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c104-127">Requirements</span></span>  
 <span data-ttu-id="6c104-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c104-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c104-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c104-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c104-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c104-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c104-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c104-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c104-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c104-132">See also</span></span>


- [<span data-ttu-id="6c104-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6c104-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
