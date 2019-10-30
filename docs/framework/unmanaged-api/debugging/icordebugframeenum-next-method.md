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
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124057"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="c6727-102">ICorDebugFrameEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="c6727-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="c6727-103">Ruft die angegebene Anzahl von ICorDebug-Frame-Instanzen ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="c6727-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6727-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6727-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6727-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6727-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c6727-106">in Die Anzahl der `ICorDebugFrame` Instanzen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c6727-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="c6727-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugFrame` Objekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="c6727-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c6727-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugFrame` Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="c6727-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="c6727-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="c6727-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6727-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6727-110">Requirements</span></span>  
 <span data-ttu-id="c6727-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6727-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6727-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6727-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6727-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6727-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6727-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6727-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
