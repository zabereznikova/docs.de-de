---
title: ICorDebugClass2 Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 905e88eb2f43850124414a42bb4e729158f9555a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405384"
---
# <a name="icordebugclass2-interface1"></a><span data-ttu-id="6f1c9-102">ICorDebugClass2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="6f1c9-102">ICorDebugClass2 Interface1</span></span>
<span data-ttu-id="6f1c9-103">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="6f1c9-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="6f1c9-104">Diese Schnittstelle erweitert [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6f1c9-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f1c9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6f1c9-105">Methods</span></span>  
  
|<span data-ttu-id="6f1c9-106">Methode</span><span class="sxs-lookup"><span data-stu-id="6f1c9-106">Method</span></span>|<span data-ttu-id="6f1c9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f1c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f1c9-108">GetParameterizedType-Methode</span><span class="sxs-lookup"><span data-stu-id="6f1c9-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="6f1c9-109">Ruft die Typdeklaration für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="6f1c9-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="6f1c9-110">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="6f1c9-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="6f1c9-111">Für jede Methode dieser Klasse legt einen Wert, der angibt, ob die Methode den benutzerdefinierten Code ist.</span><span class="sxs-lookup"><span data-stu-id="6f1c9-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f1c9-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f1c9-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f1c9-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6f1c9-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f1c9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f1c9-114">Requirements</span></span>  
 <span data-ttu-id="6f1c9-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f1c9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f1c9-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f1c9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f1c9-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f1c9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f1c9-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f1c9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1c9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f1c9-119">See Also</span></span>  
 [<span data-ttu-id="6f1c9-120">ICorDebugClass-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="6f1c9-120">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 [<span data-ttu-id="6f1c9-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f1c9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
