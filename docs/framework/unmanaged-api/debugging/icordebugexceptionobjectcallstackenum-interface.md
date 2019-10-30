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
ms.openlocfilehash: 99a700270794ca92356cb9d134cb869d456199f9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084427"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="91578-102">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91578-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="91578-103">Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="91578-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="91578-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="91578-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91578-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="91578-105">Methods</span></span>  
  
|<span data-ttu-id="91578-106">Methode</span><span class="sxs-lookup"><span data-stu-id="91578-106">Method</span></span>|<span data-ttu-id="91578-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91578-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91578-108">Icordebugexceptionobjectcallstackenum:: Next</span><span class="sxs-lookup"><span data-stu-id="91578-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="91578-109">Ruft eine angegebene Anzahl von [cordebugexceptionobjectstackframe](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) -Objekten ab, die Informationen über die Rückruf Stapel eines Ausnahme Objekts enthalten.</span><span class="sxs-lookup"><span data-stu-id="91578-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91578-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91578-110">Remarks</span></span>  
 <span data-ttu-id="91578-111">Die `ICorDebugExceptionObjectCallStackEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="91578-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="91578-112">Eine `ICorDebugExceptionObjectCallStackEnum`-Instanz wird mit [cordebugexceptionobjectstackframe](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) -Objekten aufgefüllt, indem die [icordebugexceptionobjectvalue:: enumerateexceptioncallstack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="91578-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="91578-113">Die Aufruf Listenelemente in der Auflistung können durch Aufrufen der [icordebugexceptionobjectcallstackenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="91578-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91578-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91578-114">Requirements</span></span>  
 <span data-ttu-id="91578-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91578-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91578-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91578-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91578-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91578-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91578-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91578-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91578-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91578-119">See also</span></span>

- [<span data-ttu-id="91578-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91578-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="91578-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="91578-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
