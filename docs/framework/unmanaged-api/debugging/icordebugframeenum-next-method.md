---
title: ICorDebugFrameEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 76b96dfd9d22c7e770671dcc01cb421430df729f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728185"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="3a9df-102">ICorDebugFrameEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3a9df-102">ICorDebugFrameEnum::Next Method</span></span>

<span data-ttu-id="3a9df-103">Ruft die angegebene Anzahl von ICorDebug-Frame-Instanzen ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="3a9df-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a9df-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a9df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a9df-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="3a9df-106">in Die Anzahl der `ICorDebugFrame` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="3a9df-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="3a9df-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugFrame` Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="3a9df-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3a9df-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugFrame` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="3a9df-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="3a9df-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="3a9df-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a9df-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3a9df-110">Requirements</span></span>  

 <span data-ttu-id="3a9df-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a9df-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9df-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a9df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a9df-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a9df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a9df-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a9df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
