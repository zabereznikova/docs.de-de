---
title: ICorDebugCode2::GetCodeChunks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbc7ac7d87c6a5d36dc3432c603bb7d16d62c00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747428"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="6f8a5-102">ICorDebugCode2::GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="6f8a5-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="6f8a5-103">Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.</span><span class="sxs-lookup"><span data-stu-id="6f8a5-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f8a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f8a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f8a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f8a5-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="6f8a5-106">[in] Größe der `chunks` Array.</span><span class="sxs-lookup"><span data-stu-id="6f8a5-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="6f8a5-107">[out] Die Anzahl der Blöcke, die zurückgegeben werden, der `chunks` Array.</span><span class="sxs-lookup"><span data-stu-id="6f8a5-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="6f8a5-108">[out] Ein Array von "CodeChunkInfo"-Strukturen, von denen jede einen einzelnen Codeabschnitt darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f8a5-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="6f8a5-109">Wenn der Wert des `cbufSize` gleich 0 ist, dieser Parameter kann null sein.</span><span class="sxs-lookup"><span data-stu-id="6f8a5-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f8a5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f8a5-110">Remarks</span></span>  
 <span data-ttu-id="6f8a5-111">Die Codeabschnitte werden nie überlappen, und diese folgen der Reihenfolge, in dem sie wurden durch verkettet würde [ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="6f8a5-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="6f8a5-112">Ein Codeobjekt von Microsoft intermediate Language (MSIL) in .NET Framework, Version 2.0 wird ein einzelnes Code-Segment enthalten.</span><span class="sxs-lookup"><span data-stu-id="6f8a5-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f8a5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f8a5-113">Requirements</span></span>  
 <span data-ttu-id="6f8a5-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f8a5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f8a5-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f8a5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f8a5-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f8a5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f8a5-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f8a5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8a5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f8a5-118">See also</span></span>
