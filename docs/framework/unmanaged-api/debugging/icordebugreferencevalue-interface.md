---
title: ICorDebugReferenceValue-Schnittstelle1
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
ms.openlocfilehash: 3dbe5388d7c18202f4b89269141d33463edb07a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544272"
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="f7dd0-102">ICorDebugReferenceValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="f7dd0-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="f7dd0-103">Enthält Methoden, die einen Wert zu verwalten, der einen Verweis auf ein Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="f7dd0-104">(D. h. diese Schnittstelle stellt Methoden bereit, die einen Zeiger zu verwalten.) Diese Schnittstelle implementiert "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="f7dd0-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7dd0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f7dd0-105">Methods</span></span>  
  
|<span data-ttu-id="f7dd0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f7dd0-106">Method</span></span>|<span data-ttu-id="f7dd0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7dd0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7dd0-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="f7dd0-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="f7dd0-109">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="f7dd0-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="f7dd0-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="f7dd0-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-111">Not implemented.</span></span> <span data-ttu-id="f7dd0-112">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="f7dd0-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f7dd0-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="f7dd0-114">Ruft die aktuelle Speicheradresse des referenzierten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="f7dd0-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="f7dd0-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="f7dd0-116">Ruft einen Wert, der angibt, ob dies `ICorDebugReferenceValue` ein null-Wert in diesem Fall wird die `ICorDebugReferenceValue` verweist nicht auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="f7dd0-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f7dd0-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="f7dd0-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-118">Sets the current memory address.</span></span> <span data-ttu-id="f7dd0-119">D.h., diese Methode legt für diesen `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7dd0-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7dd0-120">Remarks</span></span>  
 <span data-ttu-id="f7dd0-121">Die common Language Runtime (CLR) kann eine Garbagecollection für Objekte ausführen, wenn es sich bei der gedebuggte Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="f7dd0-122">Die Garbagecollection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="f7dd0-123">Ein `ICorDebugReferenceValue` wird entweder zusammen mit der Garbagecollection, damit die Informationen nach der Garbagecollection aktualisiert, oder er wird implizit vor der Garbagecollection ungültig gemacht.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="f7dd0-124">Die `ICorDebugReferenceValue` Objekt kann implizit ungültig werden, nachdem der gedebuggte Prozess fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="f7dd0-125">Der abgeleitete "ICorDebugHandleValue" ist nicht für ungültig erklärt, bis er explizit aufgehoben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7dd0-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7dd0-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7dd0-127">Requirements</span></span>  
 <span data-ttu-id="f7dd0-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7dd0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7dd0-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7dd0-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7dd0-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7dd0-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7dd0-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7dd0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7dd0-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7dd0-132">See also</span></span>


- [<span data-ttu-id="f7dd0-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f7dd0-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
