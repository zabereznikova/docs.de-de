---
title: ICorDebugValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue
helpviewer_keywords: ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01c94df1d8e6ddef0110268461a2b28f594201b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue-interface1"></a><span data-ttu-id="84744-102">ICorDebugValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="84744-102">ICorDebugValue Interface1</span></span>
<span data-ttu-id="84744-103">Stellt einen Wert im gedebuggten Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="84744-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="84744-104">Der Wert kann eine Lese- oder Schreibzugriff Wert sein.</span><span class="sxs-lookup"><span data-stu-id="84744-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84744-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="84744-105">Methods</span></span>  
  
|<span data-ttu-id="84744-106">Methode</span><span class="sxs-lookup"><span data-stu-id="84744-106">Method</span></span>|<span data-ttu-id="84744-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84744-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84744-108">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="84744-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="84744-109">Diese Methode wird derzeit nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="84744-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="84744-110">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="84744-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="84744-111">Ruft die Adresse dieses `ICorDebugValue` -Objekt, das gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="84744-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="84744-112">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="84744-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="84744-113">Ruft die Größe in Bytes dieses `ICorDebugValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="84744-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="84744-114">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="84744-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="84744-115">Ruft den primitiven Typ dieses `ICorDebugValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="84744-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84744-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84744-116">Remarks</span></span>  
 <span data-ttu-id="84744-117">Im Allgemeinen wird den Besitz von ein Wertobjekt übergeben, wenn es zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84744-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="84744-118">Der Empfänger ist verantwortlich für das Entfernen eines Verweises aus dem Objekt ein, wenn er mit dem Objekt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="84744-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="84744-119">Je nachdem, aus denen der Wert abgerufen wurde kann der Wert nicht gültig bleiben, nachdem der Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="84744-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="84744-120">Daher im Allgemeinen der Wert darf nicht beibehalten über einen Aufruf der der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="84744-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84744-121">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="84744-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84744-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84744-122">Requirements</span></span>  
 <span data-ttu-id="84744-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84744-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84744-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84744-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84744-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84744-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84744-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84744-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84744-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84744-127">See Also</span></span>  
    
    
    
    
 [<span data-ttu-id="84744-128">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84744-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="84744-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="84744-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
