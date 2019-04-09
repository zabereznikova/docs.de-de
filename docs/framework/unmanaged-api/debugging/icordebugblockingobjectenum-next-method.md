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
ms.openlocfilehash: 889c3bb2d5e0cd1feb9e592e667d47dedd4ede36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171144"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="2c6b5-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2c6b5-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="2c6b5-103">Ruft die angegebene Anzahl von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c6b5-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c6b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c6b5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2c6b5-106">[in] Die Anzahl der Objekte abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="2c6b5-107">[out] Ein Array von Zeigern auf [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2c6b5-108">[out] Ein Zeiger auf die Anzahl der Objekte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c6b5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c6b5-109">Return Value</span></span>  
 <span data-ttu-id="2c6b5-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="2c6b5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c6b5-111">HRESULT</span></span>|<span data-ttu-id="2c6b5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c6b5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c6b5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c6b5-113">S_OK</span></span>|<span data-ttu-id="2c6b5-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="2c6b5-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2c6b5-115">S_FALSE</span></span>|`pceltFetched` <span data-ttu-id="2c6b5-116">Ist nicht gleich `celt`.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-116">does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c6b5-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c6b5-117">Remarks</span></span>  
 <span data-ttu-id="2c6b5-118">Diese Methode funktioniert wie einen typische com-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="2c6b5-119">Die Werte für die Eingabe-Array muss mindestens der Größe `celt`.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="2c6b5-120">Das Array gefüllt entweder mit den nächsten `celt` Werte in der Enumeration und alle anderen Werte, wenn weniger als `celt` bleiben.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="2c6b5-121">Bei der Rückgabe dieser Methode `pceltFetched` wird übernommen, die Anzahl der Werte, die abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="2c6b5-122">Wenn `values` enthält ungültige Verweise oder verweist auf einen Puffer, der kleiner ist als `celt`, oder wenn `pceltFetched` ist ein ungültiger Zeiger, das Ergebnis nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c6b5-123">Obwohl die [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur wird nicht freigegeben werden müssen, die Schnittstelle "ICorDebugValue" darin freigegeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2c6b5-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c6b5-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c6b5-124">Requirements</span></span>  
 <span data-ttu-id="2c6b5-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c6b5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c6b5-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c6b5-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c6b5-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c6b5-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2c6b5-128">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2c6b5-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c6b5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c6b5-129">See also</span></span>

- [<span data-ttu-id="2c6b5-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c6b5-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="2c6b5-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2c6b5-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2c6b5-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2c6b5-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
