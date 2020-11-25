---
title: ICorDebugModuleEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: a4bdac42c584d5d34b072354de65ed20c6a80609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709491"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="ea098-102">ICorDebugModuleEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="ea098-102">ICorDebugModuleEnum::Next Method</span></span>

<span data-ttu-id="ea098-103">Ruft die Anzahl der "ICorDebug Module"-Instanzen ab, die von `celt` der-Enumeration angegeben werden, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="ea098-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea098-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea098-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea098-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea098-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="ea098-106">in Die Anzahl der `ICorDebugModule` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="ea098-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="ea098-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugModule` Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="ea098-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ea098-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugModule` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="ea098-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="ea098-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="ea098-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea098-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ea098-110">Requirements</span></span>  

 <span data-ttu-id="ea098-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea098-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea098-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea098-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea098-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea098-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea098-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea098-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea098-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea098-115">See also</span></span>
