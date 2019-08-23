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
ms.openlocfilehash: 1e94e4da0eea06ce9cc0110002b1def9e4dd4989
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939145"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="93f6d-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="93f6d-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="93f6d-103">Ruft die angegebene Anzahl von [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Objekten ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="93f6d-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93f6d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="93f6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="93f6d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="93f6d-106">in Die Anzahl der abzurufenden-Objekte.</span><span class="sxs-lookup"><span data-stu-id="93f6d-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="93f6d-107">vorgenommen Ein Array von Zeigern auf [corentbugblockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Objekte.</span><span class="sxs-lookup"><span data-stu-id="93f6d-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="93f6d-108">vorgenommen Ein Zeiger auf die Anzahl der abgerufenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="93f6d-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93f6d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="93f6d-109">Return Value</span></span>  
 <span data-ttu-id="93f6d-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="93f6d-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="93f6d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93f6d-111">HRESULT</span></span>|<span data-ttu-id="93f6d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93f6d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93f6d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="93f6d-113">S_OK</span></span>|<span data-ttu-id="93f6d-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="93f6d-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="93f6d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="93f6d-115">S_FALSE</span></span>|<span data-ttu-id="93f6d-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="93f6d-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93f6d-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93f6d-117">Remarks</span></span>  
 <span data-ttu-id="93f6d-118">Diese Methode funktioniert wie ein typischer com-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="93f6d-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="93f6d-119">Die Eingabe Array Werte müssen mindestens eine Größe `celt`aufweisen.</span><span class="sxs-lookup"><span data-stu-id="93f6d-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="93f6d-120">Das Array wird entweder mit den nächsten `celt` Werten in der-Enumeration oder mit allen verbleibenden Werten aufgefüllt, wenn weniger als `celt` vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="93f6d-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="93f6d-121">Wenn diese Methode zurückgegeben `pceltFetched` wird, wird mit der Anzahl der abgerufenen Werte aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="93f6d-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="93f6d-122">Wenn `values` ungültige Zeiger enthält oder auf einen Puffer verweist, der kleiner `celt`als ist, `pceltFetched` oder wenn ein ungültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="93f6d-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93f6d-123">Obwohl die [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Struktur nicht freigegeben werden muss, muss die Schnittstelle "ICorDebug Value" in der IT-Abteilung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="93f6d-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93f6d-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93f6d-124">Requirements</span></span>  
 <span data-ttu-id="93f6d-125">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93f6d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93f6d-126">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="93f6d-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93f6d-127">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93f6d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93f6d-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93f6d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f6d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93f6d-129">See also</span></span>

- [<span data-ttu-id="93f6d-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93f6d-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="93f6d-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="93f6d-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="93f6d-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="93f6d-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
