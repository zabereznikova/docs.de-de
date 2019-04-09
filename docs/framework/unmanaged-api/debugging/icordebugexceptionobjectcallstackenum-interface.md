---
title: ICorDebugExceptionObjectCallStackEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7ed6c04a46a767ed122e54df0695429cf923b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126203"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="e0a2a-102">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0a2a-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="e0a2a-103">Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="e0a2a-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="e0a2a-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e0a2a-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0a2a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e0a2a-105">Methods</span></span>  
  
|<span data-ttu-id="e0a2a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e0a2a-106">Method</span></span>|<span data-ttu-id="e0a2a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a2a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0a2a-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e0a2a-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="e0a2a-109">Ruft eine angegebene Anzahl von [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Objekte, die Informationen zur Aufrufliste ein Exception-Objekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="e0a2a-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0a2a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0a2a-110">Remarks</span></span>  
 <span data-ttu-id="e0a2a-111">Die `ICorDebugExceptionObjectCallStackEnum` -Schnittstelle implementiert, die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e0a2a-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="e0a2a-112">Ein `ICorDebugExceptionObjectCallStackEnum` Instanz wird mit aufgefüllt [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) -Objektpaaren durch Aufrufen der [icordebugexceptionobjectvalue:: Enumerateexceptioncallstack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e0a2a-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="e0a2a-113">Der Aufruf Stapel Elemente in der Auflistung aufgelistet werden können, durch den Aufruf der [icordebugexceptionobjectcallstackenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) Methode</span><span class="sxs-lookup"><span data-stu-id="e0a2a-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a2a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0a2a-114">Requirements</span></span>  
 <span data-ttu-id="e0a2a-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0a2a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0a2a-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0a2a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0a2a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0a2a-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e0a2a-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e0a2a-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0a2a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0a2a-119">See also</span></span>

- [<span data-ttu-id="e0a2a-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0a2a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e0a2a-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e0a2a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
