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
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695868"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="6ccb5-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ccb5-102">ICorDebugFunction3 Interface</span></span>

<span data-ttu-id="6ccb5-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="6ccb5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6ccb5-104">Erweitert die ICorDebugFunction-Schnittstelle logisch, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.</span><span class="sxs-lookup"><span data-stu-id="6ccb5-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ccb5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6ccb5-105">Methods</span></span>  
  
|<span data-ttu-id="6ccb5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="6ccb5-106">Method</span></span>|<span data-ttu-id="6ccb5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6ccb5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ccb5-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="6ccb5-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="6ccb5-109">Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="6ccb5-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ccb5-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6ccb5-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ccb5-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6ccb5-111">Requirements</span></span>  

 <span data-ttu-id="6ccb5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ccb5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ccb5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ccb5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ccb5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ccb5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ccb5-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ccb5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ccb5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ccb5-116">See also</span></span>

- [<span data-ttu-id="6ccb5-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6ccb5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6ccb5-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6ccb5-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="6ccb5-119">ReJIT: A How-To Guide</span><span class="sxs-lookup"><span data-stu-id="6ccb5-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
