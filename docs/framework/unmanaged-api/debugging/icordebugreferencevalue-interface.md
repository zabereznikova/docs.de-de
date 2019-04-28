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
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782953"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="17827-102">ICorDebugReferenceValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17827-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="17827-103">Enthält Methoden, die einen Wert zu verwalten, der einen Verweis auf ein Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="17827-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="17827-104">(D. h. diese Schnittstelle stellt Methoden bereit, die einen Zeiger zu verwalten.) Diese Schnittstelle implementiert "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="17827-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17827-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="17827-105">Methods</span></span>  
  
|<span data-ttu-id="17827-106">Methode</span><span class="sxs-lookup"><span data-stu-id="17827-106">Method</span></span>|<span data-ttu-id="17827-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17827-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17827-108">Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="17827-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="17827-109">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="17827-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="17827-110">DereferenceStrong-Methode</span><span class="sxs-lookup"><span data-stu-id="17827-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="17827-111">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="17827-111">Not implemented.</span></span> <span data-ttu-id="17827-112">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="17827-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="17827-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="17827-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="17827-114">Ruft die aktuelle Speicheradresse des referenzierten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="17827-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="17827-115">IsNull-Methode</span><span class="sxs-lookup"><span data-stu-id="17827-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="17827-116">Ruft einen Wert, der angibt, ob dies `ICorDebugReferenceValue` ein null-Wert in diesem Fall wird die `ICorDebugReferenceValue` verweist nicht auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="17827-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="17827-117">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="17827-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="17827-118">Legt die aktuelle Speicheradresse fest.</span><span class="sxs-lookup"><span data-stu-id="17827-118">Sets the current memory address.</span></span> <span data-ttu-id="17827-119">D.h., diese Methode legt für diesen `ICorDebugReferenceValue` um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="17827-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17827-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17827-120">Remarks</span></span>  
 <span data-ttu-id="17827-121">Die common Language Runtime (CLR) kann eine Garbagecollection für Objekte ausführen, wenn es sich bei der gedebuggte Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="17827-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="17827-122">Die Garbagecollection kann Objekte im Arbeitsspeicher verschieben.</span><span class="sxs-lookup"><span data-stu-id="17827-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="17827-123">Ein `ICorDebugReferenceValue` wird entweder zusammen mit der Garbagecollection, damit die Informationen nach der Garbagecollection aktualisiert, oder er wird implizit vor der Garbagecollection ungültig gemacht.</span><span class="sxs-lookup"><span data-stu-id="17827-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="17827-124">Die `ICorDebugReferenceValue` Objekt kann implizit ungültig werden, nachdem der gedebuggte Prozess fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="17827-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="17827-125">Der abgeleitete "ICorDebugHandleValue" ist nicht für ungültig erklärt, bis er explizit aufgehoben oder verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="17827-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17827-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="17827-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17827-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17827-127">Requirements</span></span>  
 <span data-ttu-id="17827-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17827-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17827-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17827-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17827-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17827-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17827-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17827-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17827-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17827-132">See also</span></span>

- [<span data-ttu-id="17827-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="17827-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
