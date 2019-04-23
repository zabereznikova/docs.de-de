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
ms.openlocfilehash: 4c29d631f84ce2dd7532e32951e71d6597218ebb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088859"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="c424c-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c424c-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="c424c-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c424c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c424c-104">Erweitert logisch die ICorDebugFunction-Schnittstelle, um Zugriff auf Code aus einer ReJIT-Anfrage zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c424c-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c424c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c424c-105">Methods</span></span>  
  
|<span data-ttu-id="c424c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="c424c-106">Method</span></span>|<span data-ttu-id="c424c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c424c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c424c-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="c424c-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="c424c-109">Ruft einen Schnittstellenzeiger auf ein [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , der die IL aus einer aktiven ReJIT-Anfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="c424c-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c424c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c424c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c424c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c424c-111">Requirements</span></span>  
 <span data-ttu-id="c424c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c424c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c424c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c424c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c424c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c424c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c424c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c424c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c424c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c424c-116">See also</span></span>

- [<span data-ttu-id="c424c-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c424c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c424c-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c424c-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c424c-119">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="c424c-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
