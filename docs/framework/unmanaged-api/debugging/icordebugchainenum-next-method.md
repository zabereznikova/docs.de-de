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
ms.openlocfilehash: 0f42020821ec71d1e59ae8097f22ee530e16a576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706176"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="44562-102">ICorDebugChainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="44562-102">ICorDebugChainEnum::Next Method</span></span>

<span data-ttu-id="44562-103">Ruft die angegebene Anzahl von ICorDebug-Ketten Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="44562-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44562-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44562-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44562-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44562-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="44562-106">in Die Anzahl der `ICorDebugChain` abzurufenden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="44562-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="44562-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugChain` Objekt verweist, das eine Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="44562-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="44562-108">vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugChain` tatsächlich zurückgegebenen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="44562-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="44562-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="44562-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44562-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="44562-110">Requirements</span></span>  

 <span data-ttu-id="44562-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44562-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44562-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44562-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44562-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44562-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44562-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44562-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
