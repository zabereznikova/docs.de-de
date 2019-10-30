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
ms.openlocfilehash: 850cbd2367dddd9f46375817e271cb8e7183cf64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121091"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="a8c7c-102">ICorDebugCode4:: enumeratevariablehomes-Methode</span><span class="sxs-lookup"><span data-stu-id="a8c7c-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="a8c7c-103">Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="a8c7c-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8c7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8c7c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8c7c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8c7c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a8c7c-106">Ein Zeiger auf die Adresse eines [icordebugvariablehomeenum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) -Schnittstellen Objekts, das ein Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="a8c7c-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8c7c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8c7c-107">Remarks</span></span>  
 <span data-ttu-id="a8c7c-108">Das [icordebugvariablehomeenum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der Schnittstelle "ICorDebugEnum" abgeleitet ist und die das Auflisten von [icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Objekten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a8c7c-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="a8c7c-109">Die Auflistung enthält möglicherweise mehrere [icorentbugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Objekte für denselben Slot-oder Argument Index, wenn Sie an unterschiedlichen Punkten in der Funktion unterschiedliche Haushalte haben.</span><span class="sxs-lookup"><span data-stu-id="a8c7c-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8c7c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8c7c-110">Requirements</span></span>  
 <span data-ttu-id="a8c7c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8c7c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8c7c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8c7c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8c7c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8c7c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8c7c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8c7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c7c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8c7c-115">See also</span></span>

- [<span data-ttu-id="a8c7c-116">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8c7c-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="a8c7c-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a8c7c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
