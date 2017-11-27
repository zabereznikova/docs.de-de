---
title: ICorDebugObjectEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72195dbf74639d5799bb96754019dddf0f30101a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="9c792-102">ICorDebugObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="9c792-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="9c792-103">Ruft den relativen virtuellen Adresse (RVA) der angegebenen Anzahl von Objekten aus der Enumeration, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="9c792-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c792-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c792-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c792-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c792-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9c792-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="9c792-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="9c792-107">[out] Ein Array von Zeigern, von denen jeder mit einem CORDB_ADDRESS-Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="9c792-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9c792-108">[out] Zeiger auf die Anzahl der tatsächlich zurückgegebenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="9c792-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="9c792-109">Dieser Wert kann null sein, wenn `celt` ist ein.</span><span class="sxs-lookup"><span data-stu-id="9c792-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c792-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c792-110">Requirements</span></span>  
 <span data-ttu-id="9c792-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c792-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c792-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c792-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c792-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c792-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c792-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c792-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c792-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c792-115">See Also</span></span>  
 
