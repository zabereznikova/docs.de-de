---
title: ICorDebugChain::GetStackRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 841e3ca608d20a4b8618508e69195de0b1da1341
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724402"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="d81c2-102">ICorDebugChain::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="d81c2-102">ICorDebugChain::GetStackRange Method</span></span>

<span data-ttu-id="d81c2-103">Ruft den Adressbereich des Stapel Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="d81c2-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d81c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d81c2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d81c2-105">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="d81c2-106">vorgenommen Ein Zeiger auf einen- `CORDB_ADDRESS` Wert, der die Startadresse des Stapel Segments ist.</span><span class="sxs-lookup"><span data-stu-id="d81c2-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="d81c2-107">vorgenommen Ein Zeiger auf einen- `CORDB_ADDRESS` Wert, der die Endadresse des Stapel Segments ist.</span><span class="sxs-lookup"><span data-stu-id="d81c2-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d81c2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d81c2-108">Remarks</span></span>  

 <span data-ttu-id="d81c2-109">Der numerische Bereich ist nur für den Vergleich von Stapel Rahmen Positionen sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="d81c2-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="d81c2-110">Sie können keine Annahmen darüber treffen, was tatsächlich im Stapel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d81c2-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81c2-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d81c2-111">Requirements</span></span>  

 <span data-ttu-id="d81c2-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d81c2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d81c2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d81c2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d81c2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d81c2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d81c2-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
