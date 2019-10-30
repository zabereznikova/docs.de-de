---
title: ICorDebugValue2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: ab5adabe868c245ed7a773d9b4206b25d9e9a4f0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140243"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="178db-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="178db-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="178db-103">Erweitert die ICorDebugValue-Schnittstelle, um die Unterstützung von ICorDebugType-Objekten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="178db-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="178db-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="178db-104">Methods</span></span>  
  
|<span data-ttu-id="178db-105">Methode</span><span class="sxs-lookup"><span data-stu-id="178db-105">Method</span></span>|<span data-ttu-id="178db-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="178db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="178db-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="178db-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="178db-108">Ruft einen Schnittstellen Zeiger auf ein `ICorDebugType` Objekt ab, das die <xref:System.Type> dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="178db-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="178db-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="178db-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="178db-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="178db-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="178db-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="178db-111">Requirements</span></span>  
 <span data-ttu-id="178db-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="178db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="178db-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="178db-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="178db-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="178db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="178db-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="178db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178db-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="178db-116">See also</span></span>

- [<span data-ttu-id="178db-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="178db-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="178db-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="178db-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
