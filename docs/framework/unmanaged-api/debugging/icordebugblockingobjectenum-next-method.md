---
title: ICorDebugBlockingObjectEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum.Next Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f2e2168ea1b03e5a2339baf019da59f1e83a71a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="5ba44-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="5ba44-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="5ba44-103">Ruft die angegebene Anzahl von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="5ba44-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ba44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ba44-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ba44-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ba44-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5ba44-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="5ba44-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="5ba44-107">[out] Ein Array von Zeigern auf [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="5ba44-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5ba44-108">[out] Ein Zeiger auf die Anzahl der Objekte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="5ba44-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ba44-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ba44-109">Return Value</span></span>  
 <span data-ttu-id="5ba44-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="5ba44-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="5ba44-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ba44-111">HRESULT</span></span>|<span data-ttu-id="5ba44-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ba44-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ba44-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ba44-113">S_OK</span></span>|<span data-ttu-id="5ba44-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5ba44-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="5ba44-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5ba44-115">S_FALSE</span></span>|<span data-ttu-id="5ba44-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="5ba44-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ba44-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ba44-117">Remarks</span></span>  
 <span data-ttu-id="5ba44-118">Diese Methode funktioniert wie einen normalen COM-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="5ba44-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="5ba44-119">Das Eingabearraywerte muss mindestens der Größe `celt`.</span><span class="sxs-lookup"><span data-stu-id="5ba44-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="5ba44-120">Das Array wird ausgefüllt werden entweder mit den nächsten `celt` von Werten in der Enumeration oder mit allen verbleibenden Werte weniger als `celt` bleiben.</span><span class="sxs-lookup"><span data-stu-id="5ba44-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="5ba44-121">Wenn diese Methode zurückgibt, `pceltFetched` wird die Anzahl der Werte, die abgerufen wurden übernommen.</span><span class="sxs-lookup"><span data-stu-id="5ba44-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="5ba44-122">Wenn `values` enthält ungültige Zeiger oder verweist auf einen Puffer, der kleiner ist als `celt`, oder wenn `pceltFetched` ist ein ungültiger Zeiger das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5ba44-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ba44-123">Obwohl die [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur muss nicht veröffentlicht werden soll, muss die Schnittstelle "ICorDebugValue" intern veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ba44-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="5ba44-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ba44-124">Requirements</span></span>  
 <span data-ttu-id="5ba44-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ba44-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ba44-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ba44-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ba44-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ba44-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ba44-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ba44-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba44-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ba44-129">See Also</span></span>  
 [<span data-ttu-id="5ba44-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ba44-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="5ba44-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ba44-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5ba44-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5ba44-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
