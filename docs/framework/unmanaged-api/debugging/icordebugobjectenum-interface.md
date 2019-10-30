---
title: ICorDebugObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: b77d5859986c90d6ef61c02547014d0bec354106
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096142"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="ccfe2-102">ICorDebugObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccfe2-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="ccfe2-103">Implementiert ICorDebugEnum-Methoden und listet Arrays von Objekten durch ihre relativen virtuellen Adressen (RVAs) auf.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ccfe2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ccfe2-104">Methods</span></span>  
  
|<span data-ttu-id="ccfe2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ccfe2-105">Method</span></span>|<span data-ttu-id="ccfe2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccfe2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ccfe2-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="ccfe2-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="ccfe2-108">Ruft die RVAs der angegebenen Anzahl von Objekten aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccfe2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ccfe2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccfe2-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ccfe2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccfe2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccfe2-111">Requirements</span></span>  
 <span data-ttu-id="ccfe2-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccfe2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccfe2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccfe2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccfe2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccfe2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccfe2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccfe2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfe2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccfe2-116">See also</span></span>

- [<span data-ttu-id="ccfe2-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ccfe2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
