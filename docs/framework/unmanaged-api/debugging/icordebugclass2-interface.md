---
title: ICorDebugClass2-Schnittstelle
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
ms.openlocfilehash: 015085cff23028814937dfef9aea19af7438b4f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173809"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="9fa7d-102">ICorDebugClass2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fa7d-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="9fa7d-103">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="9fa7d-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="9fa7d-104">Diese Schnittstelle erweitert [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9fa7d-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9fa7d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9fa7d-105">Methods</span></span>  
  
|<span data-ttu-id="9fa7d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9fa7d-106">Method</span></span>|<span data-ttu-id="9fa7d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fa7d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9fa7d-108">GetParameterizedType-Methode</span><span class="sxs-lookup"><span data-stu-id="9fa7d-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="9fa7d-109">Ruft die Deklaration des Typs für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="9fa7d-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="9fa7d-110">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="9fa7d-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="9fa7d-111">Für jede Methode dieser Klasse wird einen Wert, der angibt, ob die Methode benutzerdefinierten Code ist.</span><span class="sxs-lookup"><span data-stu-id="9fa7d-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fa7d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fa7d-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fa7d-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9fa7d-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fa7d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fa7d-114">Requirements</span></span>  
 <span data-ttu-id="9fa7d-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fa7d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa7d-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fa7d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fa7d-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fa7d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fa7d-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fa7d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa7d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fa7d-119">See also</span></span>

- [<span data-ttu-id="9fa7d-120">ICorDebugClass-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fa7d-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="9fa7d-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9fa7d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
