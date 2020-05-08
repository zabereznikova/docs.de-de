---
title: ICorDebugChainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 2d075820df534e08bdf4c2b75d36f6a60f979662
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894091"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="873d8-102">ICorDebugChainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="873d8-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="873d8-103">Ruft die angegebene Anzahl von ICorDebug-Ketten Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="873d8-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="873d8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="873d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="873d8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="873d8-106">in Die Anzahl der `ICorDebugChain` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="873d8-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="873d8-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugChain` Objekt verweist, das eine Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="873d8-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="873d8-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugChain` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="873d8-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="873d8-109">Dieser Wert kann NULL sein, `celt` wenn ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="873d8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873d8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="873d8-110">Requirements</span></span>  
 <span data-ttu-id="873d8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="873d8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="873d8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="873d8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="873d8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="873d8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="873d8-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="873d8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
