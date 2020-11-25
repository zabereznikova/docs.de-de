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
ms.openlocfilehash: 1c45faecdb8b95af8d9e981962151c2c5d071a4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731890"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="4fec9-102">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fec9-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="4fec9-103">Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="4fec9-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="4fec9-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4fec9-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fec9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4fec9-105">Methods</span></span>  
  
|<span data-ttu-id="4fec9-106">Methode</span><span class="sxs-lookup"><span data-stu-id="4fec9-106">Method</span></span>|<span data-ttu-id="4fec9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4fec9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fec9-108">Icordebugexceptionobjectcallstackenum:: Next</span><span class="sxs-lookup"><span data-stu-id="4fec9-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="4fec9-109">Ruft eine angegebene Anzahl von [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Objekten ab, die Informationen über die Rückruf Stapel eines Ausnahme Objekts enthalten.</span><span class="sxs-lookup"><span data-stu-id="4fec9-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fec9-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fec9-110">Remarks</span></span>  

 <span data-ttu-id="4fec9-111">Die `ICorDebugExceptionObjectCallStackEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4fec9-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="4fec9-112">Eine `ICorDebugExceptionObjectCallStackEnum` Instanz wird mit [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Objekten aufgefüllt, indem die [icordebugexceptionobjectvalue:: enumerateexceptioncallstack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4fec9-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="4fec9-113">Die Aufruf Listenelemente in der Auflistung können durch Aufrufen der [icordebugexceptionobjectcallstackenum:: Next](icordebugexceptionobjectcallstackenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="4fec9-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fec9-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4fec9-114">Requirements</span></span>  

 <span data-ttu-id="4fec9-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fec9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fec9-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fec9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fec9-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fec9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fec9-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fec9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fec9-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fec9-119">See also</span></span>

- [<span data-ttu-id="4fec9-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4fec9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4fec9-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4fec9-121">Debugging</span></span>](index.md)
