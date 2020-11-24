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
ms.openlocfilehash: eb8692aebe7b702b5778b3f13e496d81dcd45784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678539"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="c4bb6-102">ICorDebugThread4::GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="c4bb6-102">ICorDebugThread4::GetBlockingObjects Method</span></span>

<span data-ttu-id="c4bb6-103">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4bb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4bb6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4bb6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4bb6-105">Parameters</span></span>  

 `ppBlockingObjectEnum`  
 <span data-ttu-id="c4bb6-106">vorgenommen Ein Zeiger auf eine geordnete Enumeration von [corentbugblockingobject](cordebugblockingobject-structure.md) -Strukturen.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4bb6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4bb6-107">Remarks</span></span>  

 <span data-ttu-id="c4bb6-108">Das erste Element in der zurückgegebenen Enumeration entspricht der ersten Struktur, die den Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="c4bb6-109">Das zweite Element entspricht einem blockierenden Element, das beim Ausführen eines asynchronen Prozedur Aufrufes (APC) bei Blockierung auf dem ersten fest steht, usw.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="c4bb6-110">Die Enumeration ist nur für die Dauer des aktuellen synchronisierten Zustands gültig.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="c4bb6-111">Diese Methode muss aufgerufen werden, während sich die zu debuggende Komponente in einem synchronisierten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="c4bb6-112">Wenn `ppBlockingObjectEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="c4bb6-113">Wenn ein Thread blockiert wird und der Fehler nicht bestimmt werden kann, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt. Andernfalls wird S_OK zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4bb6-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4bb6-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4bb6-114">Requirements</span></span>  

 <span data-ttu-id="c4bb6-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4bb6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4bb6-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4bb6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4bb6-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4bb6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4bb6-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4bb6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4bb6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4bb6-119">See also</span></span>

- [<span data-ttu-id="c4bb6-120">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4bb6-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="c4bb6-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c4bb6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c4bb6-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c4bb6-122">Debugging</span></span>](index.md)
