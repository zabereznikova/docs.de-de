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
ms.openlocfilehash: c25f26bb0f1f34e3799bab4bec7e697d393cccb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784512"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="0f930-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="0f930-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="0f930-103">Ruft die angegebene Anzahl von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Objekten ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="0f930-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f930-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f930-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f930-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0f930-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0f930-106">in Die Anzahl der abzurufenden-Objekte.</span><span class="sxs-lookup"><span data-stu-id="0f930-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="0f930-107">vorgenommen Ein Array von Zeigern auf [corentbugblockingobject](cordebugblockingobject-structure.md) -Objekte.</span><span class="sxs-lookup"><span data-stu-id="0f930-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0f930-108">vorgenommen Ein Zeiger auf die Anzahl der abgerufenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="0f930-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f930-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f930-109">Return Value</span></span>  
 <span data-ttu-id="0f930-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="0f930-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="0f930-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f930-111">HRESULT</span></span>|<span data-ttu-id="0f930-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f930-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f930-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f930-113">S_OK</span></span>|<span data-ttu-id="0f930-114">Die Methode wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0f930-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="0f930-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0f930-115">S_FALSE</span></span>|<span data-ttu-id="0f930-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="0f930-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f930-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f930-117">Remarks</span></span>  
 <span data-ttu-id="0f930-118">Diese Methode funktioniert wie ein typischer com-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0f930-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="0f930-119">Die Eingabe Array Werte müssen mindestens eine `celt`Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0f930-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="0f930-120">Das Array wird entweder mit den nächsten `celt` Werten in der-Enumeration oder mit allen verbleibenden Werten gefüllt, wenn weniger als `celt` verbleiben.</span><span class="sxs-lookup"><span data-stu-id="0f930-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="0f930-121">Wenn diese Methode zurückgegeben wird, wird `pceltFetched` mit der Anzahl der abgerufenen Werte aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="0f930-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="0f930-122">Wenn `values` ungültige Zeiger enthält oder auf einen Puffer zeigt, der kleiner als `celt`ist, oder wenn `pceltFetched` ein ungültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="0f930-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f930-123">Obwohl die [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Struktur nicht freigegeben werden muss, muss die Schnittstelle "ICorDebug Value" in der IT-Abteilung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0f930-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f930-124">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f930-124">Requirements</span></span>  
 <span data-ttu-id="0f930-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f930-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f930-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f930-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f930-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f930-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f930-128">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f930-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f930-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f930-129">See also</span></span>

- [<span data-ttu-id="0f930-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f930-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="0f930-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0f930-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0f930-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0f930-132">Debugging</span></span>](index.md)
