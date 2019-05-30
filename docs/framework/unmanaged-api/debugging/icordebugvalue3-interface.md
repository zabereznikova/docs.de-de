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
ms.openlocfilehash: e4bf3605331e6900fd890e49bb3f71f4ca4409c7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377599"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="c4ea0-102">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4ea0-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="c4ea0-103">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="c4ea0-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4ea0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c4ea0-104">Methods</span></span>  
  
|<span data-ttu-id="c4ea0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c4ea0-105">Method</span></span>|<span data-ttu-id="c4ea0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4ea0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4ea0-107">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="c4ea0-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="c4ea0-108">Ruft die Größe in Bytes, davon `ICorDebugValue3` Objekt.</span><span class="sxs-lookup"><span data-stu-id="c4ea0-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4ea0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4ea0-109">Remarks</span></span>  
 <span data-ttu-id="c4ea0-110">Die [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode gibt eine Größe des Objekts, die reicht von 0 auf 2.147.483.647 Bytes.</span><span class="sxs-lookup"><span data-stu-id="c4ea0-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="c4ea0-111">In .NET Framework 4.5 kann die Größe des Arrays 2 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="c4ea0-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="c4ea0-112">Die `ICorDebugValue3` Schnittstelle können Sie die Größe dieser Arrays zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c4ea0-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ea0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4ea0-113">Requirements</span></span>  
 <span data-ttu-id="c4ea0-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4ea0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ea0-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4ea0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4ea0-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4ea0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4ea0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ea0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ea0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4ea0-118">See also</span></span>

- [<span data-ttu-id="c4ea0-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c4ea0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c4ea0-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c4ea0-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
