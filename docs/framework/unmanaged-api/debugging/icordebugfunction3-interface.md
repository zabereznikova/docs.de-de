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
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213165"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="48f0f-102">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48f0f-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="48f0f-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="48f0f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="48f0f-104">Erweitert die ICorDebugFunction-Schnittstelle logisch, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.</span><span class="sxs-lookup"><span data-stu-id="48f0f-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48f0f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="48f0f-105">Methods</span></span>  
  
|<span data-ttu-id="48f0f-106">Methode</span><span class="sxs-lookup"><span data-stu-id="48f0f-106">Method</span></span>|<span data-ttu-id="48f0f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48f0f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48f0f-108">GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="48f0f-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="48f0f-109">Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="48f0f-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48f0f-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="48f0f-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f0f-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="48f0f-111">Requirements</span></span>  
 <span data-ttu-id="48f0f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f0f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f0f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48f0f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48f0f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48f0f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48f0f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f0f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f0f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48f0f-116">See also</span></span>

- [<span data-ttu-id="48f0f-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="48f0f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="48f0f-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="48f0f-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="48f0f-119">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="48f0f-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
