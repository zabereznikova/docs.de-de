---
title: ICorDebugObjectEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: 8e188f304908a8029a57bb059046205c35346f3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724688"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="2b8bd-102">ICorDebugObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2b8bd-102">ICorDebugObjectEnum::Next Method</span></span>

<span data-ttu-id="2b8bd-103">Ruft die relativen virtuellen Adressen (RVAs) der angegebenen Anzahl von Objekten aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="2b8bd-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b8bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b8bd-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b8bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b8bd-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="2b8bd-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="2b8bd-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="2b8bd-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein CORDB_ADDRESS Objekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="2b8bd-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2b8bd-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="2b8bd-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="2b8bd-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="2b8bd-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b8bd-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2b8bd-110">Requirements</span></span>  

 <span data-ttu-id="2b8bd-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b8bd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b8bd-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b8bd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b8bd-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b8bd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b8bd-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b8bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b8bd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b8bd-115">See also</span></span>
