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
ms.openlocfilehash: 1f6a8b0ead430ffdd0e4e30cacae54d68fa9d730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969259"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="7c38a-102">ICorDebugClass2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c38a-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="7c38a-103">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="7c38a-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="7c38a-104">Diese Schnittstelle erweitert [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7c38a-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c38a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c38a-105">Methods</span></span>  
  
|<span data-ttu-id="7c38a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7c38a-106">Method</span></span>|<span data-ttu-id="7c38a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c38a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c38a-108">GetParameterizedType-Methode</span><span class="sxs-lookup"><span data-stu-id="7c38a-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="7c38a-109">Ruft die Typdeklaration für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="7c38a-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="7c38a-110">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="7c38a-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="7c38a-111">Legt für jede Methode dieser Klasse einen Wert fest, der angibt, ob es sich bei der Methode um einen benutzerdefinierten Code handelt.</span><span class="sxs-lookup"><span data-stu-id="7c38a-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c38a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c38a-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c38a-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7c38a-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c38a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c38a-114">Requirements</span></span>  
 <span data-ttu-id="7c38a-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c38a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c38a-116">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="7c38a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c38a-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c38a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c38a-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c38a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c38a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c38a-119">See also</span></span>

- [<span data-ttu-id="7c38a-120">ICorDebugClass-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c38a-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="7c38a-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c38a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
