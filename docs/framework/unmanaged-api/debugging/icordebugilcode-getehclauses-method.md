---
title: ICorDebugILCode::GetEHClauses-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e890629f307e3d3cff11dabdb2db90a5e88ece5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105053"
---
# <a name="icordebugilcodegetehclauses-method"></a><span data-ttu-id="c5754-102">ICorDebugILCode::GetEHClauses-Methode</span><span class="sxs-lookup"><span data-stu-id="c5754-102">ICorDebugILCode::GetEHClauses Method</span></span>
<span data-ttu-id="c5754-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c5754-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c5754-104">Gibt einen Zeiger auf eine Liste mit Ausnahmebehandlung (Exception Handling, EH)-Klauseln an, die für diese Intermediate Language IL definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c5754-104">Returns a pointer to a list of exception handling (EH) clauses that are defined for this intermediate language (IL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5754-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5754-105">Syntax</span></span>  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5754-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5754-106">Parameters</span></span>  
 `cClauses`  
 <span data-ttu-id="c5754-107">[in] Die Speicherkapazität für das `clauses`-Array.</span><span class="sxs-lookup"><span data-stu-id="c5754-107">[in] The storage capacity of the `clauses` array.</span></span> <span data-ttu-id="c5754-108">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="c5754-108">See the Remarks section for more information.</span></span>  
  
 `pcClauses`  
 <span data-ttu-id="c5754-109">[out] Die Anzahl der Klauseln, über die Informationen in das `clauses`-Array geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c5754-109">[out] The number of clauses about which information is written to the `clauses` array.</span></span>  
  
 <span data-ttu-id="c5754-110">Klauseln</span><span class="sxs-lookup"><span data-stu-id="c5754-110">clauses</span></span>  
 <span data-ttu-id="c5754-111">[out] Ein Array von [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) -Objekten mit Informationen zu Ausnahmebehandlungsklauseln für diese IL definiert.</span><span class="sxs-lookup"><span data-stu-id="c5754-111">[out] An array of [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) objects that contain information on exception handling clauses defined for this IL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5754-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5754-112">Remarks</span></span>  
 <span data-ttu-id="c5754-113">Wenn `cClauses` ist 0 und `pcClauses` nicht**null**, `pcClauses` auf die Anzahl der verfügbaren Ausnahmebehandlungsklauseln festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c5754-113">If `cClauses` is 0 and `pcClauses` is non-**null**, `pcClauses` is set to the number of available exception handling clauses.</span></span> <span data-ttu-id="c5754-114">Wenn `cClauses` nicht NULL ist, stellt es die Speicherkapazität des `clauses`-Arrays dar.</span><span class="sxs-lookup"><span data-stu-id="c5754-114">If `cClauses` is non-zero, it represents the storage capacity of the `clauses` array.</span></span> <span data-ttu-id="c5754-115">Bei Zurückgabe der Methode enthält `clauses` maximal `cClauses` Elemente, und `pcClauses` ist auf die Anzahl der Klauseln eingestellt, die tatsächlich in das `clauses`-Array geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="c5754-115">When the method returns, `clauses` contains a maximum of `cClauses` items, and `pcClauses` is set to the number of clauses actually written to the `clauses` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5754-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5754-116">Requirements</span></span>  
 <span data-ttu-id="c5754-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5754-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5754-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5754-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5754-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5754-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c5754-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c5754-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5754-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5754-121">See also</span></span>

- [<span data-ttu-id="c5754-122">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5754-122">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="c5754-123">CorDebugEHClause-Struktur</span><span class="sxs-lookup"><span data-stu-id="c5754-123">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)
- [<span data-ttu-id="c5754-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c5754-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
