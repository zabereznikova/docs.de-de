---
title: ICorDebugBlockingObjectEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4336978825fbf7844b3ceaf179954f28660f08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409406"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="8104e-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="8104e-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="8104e-103">Ruft die angegebene Anzahl von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="8104e-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8104e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8104e-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8104e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8104e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8104e-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="8104e-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="8104e-107">[out] Ein Array von Zeigern auf [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="8104e-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8104e-108">[out] Ein Zeiger auf die Anzahl der Objekte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="8104e-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8104e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8104e-109">Return Value</span></span>  
 <span data-ttu-id="8104e-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="8104e-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="8104e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8104e-111">HRESULT</span></span>|<span data-ttu-id="8104e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8104e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8104e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8104e-113">S_OK</span></span>|<span data-ttu-id="8104e-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8104e-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="8104e-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8104e-115">S_FALSE</span></span>|<span data-ttu-id="8104e-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="8104e-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8104e-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8104e-117">Remarks</span></span>  
 <span data-ttu-id="8104e-118">Diese Methode funktioniert wie einen normalen COM-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="8104e-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="8104e-119">Das Eingabearraywerte muss mindestens der Größe `celt`.</span><span class="sxs-lookup"><span data-stu-id="8104e-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="8104e-120">Das Array wird ausgefüllt werden entweder mit den nächsten `celt` von Werten in der Enumeration oder mit allen verbleibenden Werte weniger als `celt` bleiben.</span><span class="sxs-lookup"><span data-stu-id="8104e-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="8104e-121">Wenn diese Methode zurückgibt, `pceltFetched` wird die Anzahl der Werte, die abgerufen wurden übernommen.</span><span class="sxs-lookup"><span data-stu-id="8104e-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="8104e-122">Wenn `values` enthält ungültige Zeiger oder verweist auf einen Puffer, der kleiner ist als `celt`, oder wenn `pceltFetched` ist ein ungültiger Zeiger das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8104e-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8104e-123">Obwohl die [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur muss nicht veröffentlicht werden soll, muss die Schnittstelle "ICorDebugValue" intern veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8104e-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="8104e-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8104e-124">Requirements</span></span>  
 <span data-ttu-id="8104e-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8104e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8104e-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8104e-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8104e-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8104e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8104e-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8104e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8104e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8104e-129">See Also</span></span>  
 [<span data-ttu-id="8104e-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8104e-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="8104e-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8104e-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8104e-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8104e-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
