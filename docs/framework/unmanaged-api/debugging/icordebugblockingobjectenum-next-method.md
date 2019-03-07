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
ms.openlocfilehash: ccab0f311e51c0e82998b58f75f38359271065e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493140"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="50baf-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="50baf-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="50baf-103">Ruft die angegebene Anzahl von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="50baf-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50baf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50baf-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="50baf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50baf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="50baf-106">[in] Die Anzahl der Objekte abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="50baf-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="50baf-107">[out] Ein Array von Zeigern auf [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="50baf-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="50baf-108">[out] Ein Zeiger auf die Anzahl der Objekte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="50baf-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50baf-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50baf-109">Return Value</span></span>  
 <span data-ttu-id="50baf-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="50baf-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="50baf-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50baf-111">HRESULT</span></span>|<span data-ttu-id="50baf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50baf-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50baf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="50baf-113">S_OK</span></span>|<span data-ttu-id="50baf-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="50baf-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="50baf-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="50baf-115">S_FALSE</span></span>|<span data-ttu-id="50baf-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="50baf-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50baf-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50baf-117">Remarks</span></span>  
 <span data-ttu-id="50baf-118">Diese Methode funktioniert wie einen typische com-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="50baf-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="50baf-119">Die Werte für die Eingabe-Array muss mindestens der Größe `celt`.</span><span class="sxs-lookup"><span data-stu-id="50baf-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="50baf-120">Das Array gefüllt entweder mit den nächsten `celt` Werte in der Enumeration und alle anderen Werte, wenn weniger als `celt` bleiben.</span><span class="sxs-lookup"><span data-stu-id="50baf-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="50baf-121">Bei der Rückgabe dieser Methode `pceltFetched` wird übernommen, die Anzahl der Werte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="50baf-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="50baf-122">Wenn `values` enthält ungültige Verweise oder verweist auf einen Puffer, der kleiner ist als `celt`, oder wenn `pceltFetched` ist ein ungültiger Zeiger, das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="50baf-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50baf-123">Obwohl die [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur wird nicht freigegeben werden müssen, die Schnittstelle "ICorDebugValue" darin freigegeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="50baf-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50baf-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50baf-124">Requirements</span></span>  
 <span data-ttu-id="50baf-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50baf-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50baf-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50baf-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50baf-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50baf-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50baf-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50baf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50baf-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50baf-129">See also</span></span>
- [<span data-ttu-id="50baf-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50baf-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="50baf-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50baf-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="50baf-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="50baf-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
