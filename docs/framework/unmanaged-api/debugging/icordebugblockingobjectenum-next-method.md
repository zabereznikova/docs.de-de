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
ms.openlocfilehash: 232068a5fee8f7bd3dfbddf4d9452e80d6fd6170
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719189"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="f3a9e-102">ICorDebugBlockingObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f3a9e-102">ICorDebugBlockingObjectEnum::Next Method</span></span>

<span data-ttu-id="f3a9e-103">Ruft die angegebene Anzahl von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Objekten ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3a9e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3a9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3a9e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f3a9e-106">in Die Anzahl der abzurufenden-Objekte.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="f3a9e-107">vorgenommen Ein Array von Zeigern auf [corentbugblockingobject](cordebugblockingobject-structure.md) -Objekte.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f3a9e-108">vorgenommen Ein Zeiger auf die Anzahl der abgerufenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3a9e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3a9e-109">Return Value</span></span>  

 <span data-ttu-id="f3a9e-110">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="f3a9e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3a9e-111">HRESULT</span></span>|<span data-ttu-id="f3a9e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f3a9e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3a9e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3a9e-113">S_OK</span></span>|<span data-ttu-id="f3a9e-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f3a9e-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f3a9e-115">S_FALSE</span></span>|<span data-ttu-id="f3a9e-116">`pceltFetched` entspricht nicht `celt`.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3a9e-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3a9e-117">Remarks</span></span>  

 <span data-ttu-id="f3a9e-118">Diese Methode funktioniert wie ein typischer com-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="f3a9e-119">Die Eingabe Array Werte müssen mindestens eine Größe aufweisen `celt` .</span><span class="sxs-lookup"><span data-stu-id="f3a9e-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="f3a9e-120">Das Array wird entweder mit den nächsten `celt` Werten in der-Enumeration oder mit allen verbleibenden Werten aufgefüllt, wenn weniger als vorhanden `celt` sind.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="f3a9e-121">Wenn diese Methode zurückgegeben wird, `pceltFetched` wird mit der Anzahl der abgerufenen Werte aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="f3a9e-122">Wenn `values` ungültige Zeiger enthält oder auf einen Puffer verweist, der kleiner als ist `celt` , oder wenn `pceltFetched` ein ungültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3a9e-123">Obwohl die [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Struktur nicht freigegeben werden muss, muss die Schnittstelle "ICorDebug Value" in der IT-Abteilung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f3a9e-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a9e-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f3a9e-124">Requirements</span></span>  

 <span data-ttu-id="f3a9e-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3a9e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a9e-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3a9e-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3a9e-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3a9e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3a9e-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a9e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a9e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3a9e-129">See also</span></span>

- [<span data-ttu-id="f3a9e-130">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3a9e-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="f3a9e-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3a9e-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f3a9e-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f3a9e-132">Debugging</span></span>](index.md)
