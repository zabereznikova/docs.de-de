---
title: 'ICorDebugCode4:: enumeratevariablehomes-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 6d58efa5629bb02158a275dec61c0313bca821a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720751"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="5fc47-102">ICorDebugCode4:: enumeratevariablehomes-Methode</span><span class="sxs-lookup"><span data-stu-id="5fc47-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>

<span data-ttu-id="5fc47-103">Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="5fc47-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fc47-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fc47-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fc47-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="5fc47-106">Ein Zeiger auf die Adresse eines [icordebugvariablehomeenum](icordebugvariablehomeenum-interface.md) -Schnittstellen Objekts, das ein Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="5fc47-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fc47-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fc47-107">Remarks</span></span>  

 <span data-ttu-id="5fc47-108">Das [icordebugvariablehomeenum](icordebugvariablehomeenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der Schnittstelle "ICorDebugEnum" abgeleitet ist und die das Auflisten von [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5fc47-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="5fc47-109">Die Auflistung enthält möglicherweise mehrere [icorentbugvariablehome](icordebugvariablehome-interface.md) -Objekte für denselben Slot-oder Argument Index, wenn Sie an unterschiedlichen Punkten in der Funktion unterschiedliche Haushalte haben.</span><span class="sxs-lookup"><span data-stu-id="5fc47-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fc47-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5fc47-110">Requirements</span></span>  

 <span data-ttu-id="5fc47-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fc47-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc47-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fc47-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fc47-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fc47-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fc47-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc47-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc47-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5fc47-115">See also</span></span>

- [<span data-ttu-id="5fc47-116">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fc47-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="5fc47-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fc47-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
