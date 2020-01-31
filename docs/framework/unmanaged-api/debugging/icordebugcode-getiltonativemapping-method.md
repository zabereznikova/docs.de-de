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
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777891"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="277ec-102">ICorDebugCode::GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="277ec-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="277ec-103">Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen ab, die Zuordnungen von MSIL-Offsets (Microsoft Intermediate Language) zu nativen Offsets darstellen.</span><span class="sxs-lookup"><span data-stu-id="277ec-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="277ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="277ec-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="277ec-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="277ec-106">[in] Die Größe des `map`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="277ec-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="277ec-107">vorgenommen Ein Zeiger auf die tatsächliche Anzahl der Elemente, die im `map` Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="277ec-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="277ec-108">vorgenommen Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen, von denen jedes eine Zuordnung von einem MSIL-Offset zu einem systemeigenen Offset darstellt.</span><span class="sxs-lookup"><span data-stu-id="277ec-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="277ec-109">Es gibt keine Reihenfolge für das Array von Elementen, die zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="277ec-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="277ec-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="277ec-110">Remarks</span></span>  
 <span data-ttu-id="277ec-111">Die `GetILToNativeMapping`-Methode gibt nur dann sinnvolle Ergebnisse zurück, wenn diese "ICorDebugCode"-Instanz systemeigenen Code darstellt, der Just-in-time (JIT) aus MSIL-Code kompiliert hat.</span><span class="sxs-lookup"><span data-stu-id="277ec-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="277ec-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="277ec-112">Requirements</span></span>  
 <span data-ttu-id="277ec-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="277ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="277ec-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="277ec-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="277ec-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="277ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="277ec-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="277ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277ec-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="277ec-117">See also</span></span>

- [<span data-ttu-id="277ec-118">ICorDebugCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="277ec-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
