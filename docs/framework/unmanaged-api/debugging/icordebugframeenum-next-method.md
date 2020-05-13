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
ms.openlocfilehash: 4652e4b34d614ad3b7b852925fcc63309bdd1498
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209460"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="33e67-102">ICorDebugFrameEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="33e67-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="33e67-103">Ruft die angegebene Anzahl von ICorDebug-Frame-Instanzen ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="33e67-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33e67-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33e67-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33e67-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="33e67-106">in Die Anzahl der `ICorDebugFrame` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="33e67-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="33e67-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugFrame` Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="33e67-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="33e67-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugFrame` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="33e67-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="33e67-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="33e67-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e67-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="33e67-110">Requirements</span></span>  
 <span data-ttu-id="33e67-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33e67-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e67-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33e67-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33e67-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33e67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33e67-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
