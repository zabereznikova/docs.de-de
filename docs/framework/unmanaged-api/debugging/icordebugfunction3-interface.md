---
title: ICorDebugFunction3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: b74008e0a183d46d82c5262209d582537fd155c7
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938083"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="31a68-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31a68-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="31a68-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="31a68-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="31a68-104">Erweitert die ICorDebugFunction-Schnittstelle logisch, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.</span><span class="sxs-lookup"><span data-stu-id="31a68-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31a68-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="31a68-105">Methods</span></span>  
  
|<span data-ttu-id="31a68-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="31a68-106">Method</span></span>|<span data-ttu-id="31a68-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31a68-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31a68-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="31a68-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="31a68-109">Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="31a68-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31a68-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31a68-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31a68-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31a68-111">Requirements</span></span>  
 <span data-ttu-id="31a68-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31a68-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31a68-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31a68-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31a68-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31a68-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31a68-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31a68-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a68-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31a68-116">See also</span></span>

- [<span data-ttu-id="31a68-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="31a68-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="31a68-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="31a68-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="31a68-119">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="31a68-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
