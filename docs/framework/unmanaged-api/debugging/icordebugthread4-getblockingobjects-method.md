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
ms.openlocfilehash: 39833b689f28437b4241d9cb15fb4a92b2f9bcc3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791373"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="03ad8-102">ICorDebugThread4::GetBlockingObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="03ad8-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="03ad8-103">Stellt eine geordnete Enumeration von [CorDebugBlockingObject](cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="03ad8-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ad8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03ad8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="03ad8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="03ad8-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="03ad8-106">vorgenommen Ein Zeiger auf eine geordnete Enumeration von [corentbugblockingobject](cordebugblockingobject-structure.md) -Strukturen.</span><span class="sxs-lookup"><span data-stu-id="03ad8-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03ad8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03ad8-107">Remarks</span></span>  
 <span data-ttu-id="03ad8-108">Das erste Element in der zurückgegebenen Enumeration entspricht der ersten Struktur, die den Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="03ad8-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="03ad8-109">Das zweite Element entspricht einem blockierenden Element, das beim Ausführen eines asynchronen Prozedur Aufrufes (APC) bei Blockierung auf dem ersten fest steht, usw.</span><span class="sxs-lookup"><span data-stu-id="03ad8-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="03ad8-110">Die Enumeration ist nur für die Dauer des aktuellen synchronisierten Zustands gültig.</span><span class="sxs-lookup"><span data-stu-id="03ad8-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="03ad8-111">Diese Methode muss aufgerufen werden, während sich die zu debuggende Komponente in einem synchronisierten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="03ad8-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="03ad8-112">Wenn `ppBlockingObjectEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="03ad8-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="03ad8-113">Wenn ein Thread blockiert wird und der Fehler nicht bestimmt werden kann, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt. Andernfalls wird S_OK zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="03ad8-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03ad8-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03ad8-114">Requirements</span></span>  
 <span data-ttu-id="03ad8-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03ad8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ad8-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03ad8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03ad8-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03ad8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03ad8-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03ad8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ad8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03ad8-119">See also</span></span>

- [<span data-ttu-id="03ad8-120">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03ad8-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="03ad8-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="03ad8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="03ad8-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="03ad8-122">Debugging</span></span>](index.md)
