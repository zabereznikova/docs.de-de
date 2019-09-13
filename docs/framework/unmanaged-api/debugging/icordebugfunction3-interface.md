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
ms.openlocfilehash: a3eebdf56796fe599ec6ff62d7008d1af3be796e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926838"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="445a4-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="445a4-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="445a4-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="445a4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="445a4-104">Erweitert die ICorDebugFunction-Schnittstelle logisch, um den Zugriff auf Code über eine ReJIT-Anforderung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="445a4-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="445a4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="445a4-105">Methods</span></span>  
  
|<span data-ttu-id="445a4-106">Methode</span><span class="sxs-lookup"><span data-stu-id="445a4-106">Method</span></span>|<span data-ttu-id="445a4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="445a4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="445a4-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="445a4-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="445a4-109">Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="445a4-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="445a4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="445a4-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="445a4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="445a4-111">Requirements</span></span>  
 <span data-ttu-id="445a4-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="445a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="445a4-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="445a4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="445a4-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="445a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="445a4-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="445a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445a4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="445a4-116">See also</span></span>

- [<span data-ttu-id="445a4-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="445a4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="445a4-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="445a4-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="445a4-119">ReJIT Leitfaden</span><span class="sxs-lookup"><span data-stu-id="445a4-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
