---
title: ICorDebugThread4::GetBlockingObjects-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 366b5124cc66a4e9a1c3bd4e77f604f15ba8d8a8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379672"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="2620a-102">ICorDebugThread4::GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="2620a-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="2620a-103">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2620a-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2620a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2620a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="2620a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2620a-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="2620a-106">vorgenommen Ein Zeiger auf eine geordnete Enumeration von [corentbugblockingobject](cordebugblockingobject-structure.md) -Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2620a-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2620a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2620a-107">Remarks</span></span>  
 <span data-ttu-id="2620a-108">Das erste Element in der zurückgegebenen Enumeration entspricht der ersten Struktur, die den Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="2620a-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="2620a-109">Das zweite Element entspricht einem blockierenden Element, das beim Ausführen eines asynchronen Prozedur Aufrufes (APC) bei Blockierung auf dem ersten fest steht, usw.</span><span class="sxs-lookup"><span data-stu-id="2620a-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="2620a-110">Die Enumeration ist nur für die Dauer des aktuellen synchronisierten Zustands gültig.</span><span class="sxs-lookup"><span data-stu-id="2620a-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="2620a-111">Diese Methode muss aufgerufen werden, während sich die zu debuggende Komponente in einem synchronisierten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="2620a-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="2620a-112">Wenn `ppBlockingObjectEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="2620a-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="2620a-113">Wenn ein Thread blockiert wird und der Fehler nicht bestimmt werden kann, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt. Andernfalls wird S_OK zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2620a-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2620a-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2620a-114">Requirements</span></span>  
 <span data-ttu-id="2620a-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2620a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2620a-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2620a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2620a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2620a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2620a-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2620a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2620a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2620a-119">See also</span></span>

- [<span data-ttu-id="2620a-120">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2620a-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="2620a-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2620a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2620a-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2620a-122">Debugging</span></span>](index.md)
