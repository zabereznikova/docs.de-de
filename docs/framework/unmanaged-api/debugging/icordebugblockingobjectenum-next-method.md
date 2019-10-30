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
ms.openlocfilehash: 3a1c4a931a61186c4737aada47ceb861e7848e7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122830"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="75674-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="75674-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="75674-103">Ruft die angegebene Anzahl von [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Objekten ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="75674-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75674-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75674-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="75674-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="75674-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="75674-106">in Die Anzahl der abzurufenden-Objekte.</span><span class="sxs-lookup"><span data-stu-id="75674-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="75674-107">vorgenommen Ein Array von Zeigern auf [corentbugblockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Objekte.</span><span class="sxs-lookup"><span data-stu-id="75674-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="75674-108">vorgenommen Ein Zeiger auf die Anzahl der abgerufenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="75674-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75674-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="75674-109">Return Value</span></span>  
 <span data-ttu-id="75674-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="75674-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="75674-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75674-111">HRESULT</span></span>|<span data-ttu-id="75674-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75674-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75674-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="75674-113">S_OK</span></span>|<span data-ttu-id="75674-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="75674-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="75674-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="75674-115">S_FALSE</span></span>|<span data-ttu-id="75674-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="75674-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75674-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75674-117">Remarks</span></span>  
 <span data-ttu-id="75674-118">Diese Methode funktioniert wie ein typischer com-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="75674-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="75674-119">Die Eingabe Array Werte müssen mindestens eine `celt`Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="75674-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="75674-120">Das Array wird entweder mit den nächsten `celt` Werten in der-Enumeration oder mit allen verbleibenden Werten gefüllt, wenn weniger als `celt` verbleiben.</span><span class="sxs-lookup"><span data-stu-id="75674-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="75674-121">Wenn diese Methode zurückgegeben wird, wird `pceltFetched` mit der Anzahl der abgerufenen Werte aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="75674-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="75674-122">Wenn `values` ungültige Zeiger enthält oder auf einen Puffer zeigt, der kleiner als `celt`ist, oder wenn `pceltFetched` ein ungültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="75674-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75674-123">Obwohl die [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Struktur nicht freigegeben werden muss, muss die Schnittstelle "ICorDebug Value" in der IT-Abteilung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="75674-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75674-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75674-124">Requirements</span></span>  
 <span data-ttu-id="75674-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75674-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75674-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75674-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75674-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75674-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75674-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75674-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75674-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75674-129">See also</span></span>

- [<span data-ttu-id="75674-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75674-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="75674-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="75674-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="75674-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="75674-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
