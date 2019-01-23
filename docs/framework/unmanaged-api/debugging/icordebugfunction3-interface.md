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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e564ce63f7bf9e04ebf9a0bdcfc819ea23b3b2ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515559"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="94a28-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94a28-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="94a28-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="94a28-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="94a28-104">Erweitert logisch die ICorDebugFunction-Schnittstelle, um Zugriff auf Code aus einer ReJIT-Anfrage zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="94a28-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94a28-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="94a28-105">Methods</span></span>  
  
|<span data-ttu-id="94a28-106">Methode</span><span class="sxs-lookup"><span data-stu-id="94a28-106">Method</span></span>|<span data-ttu-id="94a28-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94a28-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94a28-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="94a28-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="94a28-109">Ruft einen Schnittstellenzeiger auf ein [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , der die IL aus einer aktiven ReJIT-Anfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="94a28-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94a28-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94a28-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a28-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94a28-111">Requirements</span></span>  
 <span data-ttu-id="94a28-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a28-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a28-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a28-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a28-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a28-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a28-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a28-116">See also</span></span>
- [<span data-ttu-id="94a28-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="94a28-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="94a28-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="94a28-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="94a28-119">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="94a28-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
