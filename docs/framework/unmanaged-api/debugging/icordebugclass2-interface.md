---
title: ICorDebugClass2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2
helpviewer_keywords: ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c4f96f084a96ccdc9857a64217284b485aa73a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugclass2-interface1"></a><span data-ttu-id="fc3f9-102">ICorDebugClass2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="fc3f9-102">ICorDebugClass2 Interface1</span></span>
<span data-ttu-id="fc3f9-103">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="fc3f9-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="fc3f9-104">Diese Schnittstelle erweitert [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fc3f9-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc3f9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fc3f9-105">Methods</span></span>  
  
|<span data-ttu-id="fc3f9-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fc3f9-106">Method</span></span>|<span data-ttu-id="fc3f9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc3f9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc3f9-108">GetParameterizedType-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3f9-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="fc3f9-109">Ruft die Typdeklaration für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="fc3f9-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="fc3f9-110">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3f9-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="fc3f9-111">Für jede Methode dieser Klasse legt einen Wert, der angibt, ob die Methode den benutzerdefinierten Code ist.</span><span class="sxs-lookup"><span data-stu-id="fc3f9-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc3f9-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc3f9-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc3f9-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fc3f9-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3f9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc3f9-114">Requirements</span></span>  
 <span data-ttu-id="fc3f9-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3f9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3f9-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc3f9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc3f9-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc3f9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc3f9-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc3f9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3f9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc3f9-119">See Also</span></span>  
 [<span data-ttu-id="fc3f9-120">ICorDebugClass Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="fc3f9-120">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 [<span data-ttu-id="fc3f9-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fc3f9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
