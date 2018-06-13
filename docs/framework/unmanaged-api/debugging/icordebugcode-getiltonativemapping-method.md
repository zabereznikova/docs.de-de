---
title: ICorDebugCode::GetILToNativeMapping-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13ec60999db88b9d7191a3866fcebe8098b4edee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411385"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="12360-102">ICorDebugCode::GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="12360-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="12360-103">Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen, die Zuordnungen von Microsoft intermediate Language (MSIL)-offsets und systemeigenen Offsets darstellen.</span><span class="sxs-lookup"><span data-stu-id="12360-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12360-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12360-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12360-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12360-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="12360-106">[in] Die Größe des `map`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="12360-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="12360-107">[out] Ein Zeiger auf die tatsächliche Anzahl der zurückgegebenen Elemente der `map` Array.</span><span class="sxs-lookup"><span data-stu-id="12360-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="12360-108">[out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP` -Strukturen, von denen jede eine Zuordnung von MSIL-Offset zu einem systemeigenen Offset darstellt.</span><span class="sxs-lookup"><span data-stu-id="12360-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="12360-109">Es gibt keine Reihenfolge für das Array von Elementen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="12360-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12360-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12360-110">Remarks</span></span>  
 <span data-ttu-id="12360-111">Die `GetILToNativeMapping` Methodenrückgabe aussagekräftige Ergebnisse nur, wenn diese "ICorDebugCode"-Instanz systemeigenen Code, die just darstellt-in-Time (JIT) über MSIL-Code kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="12360-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12360-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12360-112">Requirements</span></span>  
 <span data-ttu-id="12360-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12360-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12360-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12360-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12360-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12360-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12360-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12360-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12360-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12360-117">See Also</span></span>  
 [<span data-ttu-id="12360-118">ICorDebugCode-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="12360-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
