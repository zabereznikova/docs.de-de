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
ms.openlocfilehash: c05420a54d7a79198e235a39e578bedf296b4fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="523a8-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="523a8-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="523a8-103">Ruft die angegebene Anzahl von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="523a8-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="523a8-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingOjbect values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="523a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="523a8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="523a8-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="523a8-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="523a8-107">[out] Ein Array von Zeigern auf [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="523a8-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="523a8-108">[out] Ein Zeiger auf die Anzahl der Objekte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="523a8-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="523a8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="523a8-109">Return Value</span></span>  
 <span data-ttu-id="523a8-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="523a8-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="523a8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="523a8-111">HRESULT</span></span>|<span data-ttu-id="523a8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="523a8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="523a8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="523a8-113">S_OK</span></span>|<span data-ttu-id="523a8-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="523a8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="523a8-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="523a8-115">S_FALSE</span></span>|<span data-ttu-id="523a8-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="523a8-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="523a8-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="523a8-117">Remarks</span></span>  
 <span data-ttu-id="523a8-118">Diese Methode funktioniert wie einen normalen COM-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="523a8-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="523a8-119">Das Eingabearraywerte muss mindestens der Größe `celt`.</span><span class="sxs-lookup"><span data-stu-id="523a8-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="523a8-120">Das Array wird ausgefüllt werden entweder mit den nächsten `celt` von Werten in der Enumeration oder mit allen verbleibenden Werte weniger als `celt` bleiben.</span><span class="sxs-lookup"><span data-stu-id="523a8-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="523a8-121">Wenn diese Methode zurückgibt, `pceltFetched` wird die Anzahl der Werte, die abgerufen wurden übernommen.</span><span class="sxs-lookup"><span data-stu-id="523a8-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="523a8-122">Wenn `values` enthält ungültige Zeiger oder verweist auf einen Puffer, der kleiner ist als `celt`, oder wenn `pceltFetched` ist ein ungültiger Zeiger das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="523a8-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="523a8-123">Obwohl die [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur muss nicht veröffentlicht werden soll, muss die Schnittstelle "ICorDebugValue" intern veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="523a8-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="523a8-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="523a8-124">Requirements</span></span>  
 <span data-ttu-id="523a8-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="523a8-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="523a8-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="523a8-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="523a8-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="523a8-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="523a8-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="523a8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523a8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="523a8-129">See Also</span></span>  
 [<span data-ttu-id="523a8-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="523a8-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="523a8-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="523a8-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="523a8-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="523a8-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
