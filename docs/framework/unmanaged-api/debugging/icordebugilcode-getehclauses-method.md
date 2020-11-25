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
ms.openlocfilehash: 38936a57944e9a0920c374f473c4cbe8e8d70abb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728666"
---
# <a name="icordebugilcodegetehclauses-method"></a><span data-ttu-id="6196e-102">ICorDebugILCode::GetEHClauses-Methode</span><span class="sxs-lookup"><span data-stu-id="6196e-102">ICorDebugILCode::GetEHClauses Method</span></span>

<span data-ttu-id="6196e-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="6196e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6196e-104">Gibt einen Zeiger auf eine Liste mit Ausnahmebehandlung (Exception Handling, EH)-Klauseln an, die für diese Intermediate Language IL definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6196e-104">Returns a pointer to a list of exception handling (EH) clauses that are defined for this intermediate language (IL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6196e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6196e-105">Syntax</span></span>  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6196e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6196e-106">Parameters</span></span>  

 `cClauses`  
 <span data-ttu-id="6196e-107">[in] Die Speicherkapazität für das `clauses`-Array.</span><span class="sxs-lookup"><span data-stu-id="6196e-107">[in] The storage capacity of the `clauses` array.</span></span> <span data-ttu-id="6196e-108">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="6196e-108">See the Remarks section for more information.</span></span>  
  
 `pcClauses`  
 <span data-ttu-id="6196e-109">[out] Die Anzahl der Klauseln, über die Informationen in das `clauses`-Array geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6196e-109">[out] The number of clauses about which information is written to the `clauses` array.</span></span>  
  
 <span data-ttu-id="6196e-110">Klauseln</span><span class="sxs-lookup"><span data-stu-id="6196e-110">clauses</span></span>  
 <span data-ttu-id="6196e-111">vorgenommen Ein Array von [cordebugehclause](cordebugehclause-structure.md) -Objekten, die Informationen zu Ausnahme Behandlungs Klauseln enthalten, die für diese Il definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6196e-111">[out] An array of [CorDebugEHClause](cordebugehclause-structure.md) objects that contain information on exception handling clauses defined for this IL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6196e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6196e-112">Remarks</span></span>  

 <span data-ttu-id="6196e-113">Wenn `cClauses` 0 (null) und ungleich `pcClauses` **null** ist, `pcClauses` wird auf die Anzahl der verfügbaren Klauseln für die Ausnahmebehandlung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6196e-113">If `cClauses` is 0 and `pcClauses` is non-**null**, `pcClauses` is set to the number of available exception handling clauses.</span></span> <span data-ttu-id="6196e-114">Wenn `cClauses` nicht NULL ist, stellt es die Speicherkapazität des `clauses`-Arrays dar.</span><span class="sxs-lookup"><span data-stu-id="6196e-114">If `cClauses` is non-zero, it represents the storage capacity of the `clauses` array.</span></span> <span data-ttu-id="6196e-115">Bei Zurückgabe der Methode enthält `clauses` maximal `cClauses` Elemente, und `pcClauses` ist auf die Anzahl der Klauseln eingestellt, die tatsächlich in das `clauses`-Array geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="6196e-115">When the method returns, `clauses` contains a maximum of `cClauses` items, and `pcClauses` is set to the number of clauses actually written to the `clauses` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6196e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6196e-116">Requirements</span></span>  

 <span data-ttu-id="6196e-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6196e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6196e-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6196e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6196e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6196e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6196e-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6196e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6196e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6196e-121">See also</span></span>

- [<span data-ttu-id="6196e-122">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6196e-122">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="6196e-123">CorDebugEHClause-Struktur</span><span class="sxs-lookup"><span data-stu-id="6196e-123">CorDebugEHClause Structure</span></span>](cordebugehclause-structure.md)
- [<span data-ttu-id="6196e-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6196e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
