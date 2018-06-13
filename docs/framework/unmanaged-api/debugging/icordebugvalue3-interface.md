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
ms.openlocfilehash: d70a6f5c1df771c514f5f91770b4c53c55fec364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420661"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="619aa-102">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="619aa-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="619aa-103">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="619aa-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="619aa-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="619aa-104">Methods</span></span>  
  
|<span data-ttu-id="619aa-105">Methode</span><span class="sxs-lookup"><span data-stu-id="619aa-105">Method</span></span>|<span data-ttu-id="619aa-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="619aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="619aa-107">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="619aa-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="619aa-108">Ruft die Größe in Bytes dieses `ICorDebugValue3` Objekt.</span><span class="sxs-lookup"><span data-stu-id="619aa-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="619aa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="619aa-109">Remarks</span></span>  
 <span data-ttu-id="619aa-110">Die [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methodenrückgabe ein Objektgröße, die Bereiche von 0 bis 2.147.483.647 Byte.</span><span class="sxs-lookup"><span data-stu-id="619aa-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="619aa-111">In der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], die Größe des Arrays kann maximal 2 GB.</span><span class="sxs-lookup"><span data-stu-id="619aa-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="619aa-112">Die `ICorDebugValue3` -Schnittstelle ermöglicht Ihnen die Größe dieser Arrays bestimmt.</span><span class="sxs-lookup"><span data-stu-id="619aa-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="619aa-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="619aa-113">Requirements</span></span>  
 <span data-ttu-id="619aa-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="619aa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="619aa-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="619aa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="619aa-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="619aa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="619aa-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="619aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619aa-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="619aa-118">See Also</span></span>  
    
    
 [<span data-ttu-id="619aa-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="619aa-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="619aa-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="619aa-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
