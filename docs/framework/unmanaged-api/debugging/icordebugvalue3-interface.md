---
title: ICorDebugValue3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300d2263c076c9028340863e2f7a3fa27a36ef9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221976"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="b9a8f-102">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9a8f-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="b9a8f-103">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="b9a8f-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9a8f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b9a8f-104">Methods</span></span>  
  
|<span data-ttu-id="b9a8f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b9a8f-105">Method</span></span>|<span data-ttu-id="b9a8f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9a8f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9a8f-107">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="b9a8f-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="b9a8f-108">Ruft die Größe in Bytes, davon `ICorDebugValue3` Objekt.</span><span class="sxs-lookup"><span data-stu-id="b9a8f-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9a8f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9a8f-109">Remarks</span></span>  
 <span data-ttu-id="b9a8f-110">Die [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode gibt eine Größe des Objekts, die reicht von 0 auf 2.147.483.647 Bytes.</span><span class="sxs-lookup"><span data-stu-id="b9a8f-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="b9a8f-111">In der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], die Größe des Arrays kann maximal 2 GB.</span><span class="sxs-lookup"><span data-stu-id="b9a8f-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="b9a8f-112">Die `ICorDebugValue3` Schnittstelle können Sie die Größe dieser Arrays zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b9a8f-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a8f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9a8f-113">Requirements</span></span>  
 <span data-ttu-id="b9a8f-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9a8f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a8f-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9a8f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9a8f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9a8f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9a8f-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9a8f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a8f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9a8f-118">See also</span></span>

- [<span data-ttu-id="b9a8f-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b9a8f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b9a8f-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b9a8f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
