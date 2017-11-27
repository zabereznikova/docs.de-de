---
title: ICorDebugFunction3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction3
api_location: mscordbi.dll
api_type: COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfe0c420c1c9b8074b7cb769e592f8cb2f5916e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="f190b-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f190b-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="f190b-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f190b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f190b-104">Erweitert logisch die ICorDebugFunction-Schnittstelle, um den Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.</span><span class="sxs-lookup"><span data-stu-id="f190b-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f190b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f190b-105">Methods</span></span>  
  
|<span data-ttu-id="f190b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f190b-106">Method</span></span>|<span data-ttu-id="f190b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f190b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f190b-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="f190b-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="f190b-109">Ruft einen Schnittstellenzeiger auf eine [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , der die IL aus einer aktiven ReJIT-Anfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="f190b-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f190b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f190b-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f190b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f190b-111">Requirements</span></span>  
 <span data-ttu-id="f190b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f190b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f190b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f190b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f190b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f190b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f190b-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f190b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f190b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f190b-116">See Also</span></span>  
 [<span data-ttu-id="f190b-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f190b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f190b-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f190b-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="f190b-119">ReJIT: Eine Anleitung</span><span class="sxs-lookup"><span data-stu-id="f190b-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
