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
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178954"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="b2fe7-102">ICorDebugChain::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="b2fe7-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="b2fe7-103">Ruft den Adressbereich des Stapelsegments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="b2fe7-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2fe7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2fe7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2fe7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2fe7-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="b2fe7-106">[out] Ein Zeiger auf `CORDB_ADDRESS` einen Wert, der die Startadresse des Stapelsegments ist.</span><span class="sxs-lookup"><span data-stu-id="b2fe7-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="b2fe7-107">[out] Ein Zeiger auf `CORDB_ADDRESS` einen Wert, der die Endadresse des Stapelsegments ist.</span><span class="sxs-lookup"><span data-stu-id="b2fe7-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2fe7-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b2fe7-108">Remarks</span></span>  
 <span data-ttu-id="b2fe7-109">Der numerische Bereich ist nur für den Vergleich von Stapelrahmenpositionen sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="b2fe7-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="b2fe7-110">Sie können keine Annahmen darüber treffen, was tatsächlich auf dem Stapel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b2fe7-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2fe7-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2fe7-111">Requirements</span></span>  
 <span data-ttu-id="b2fe7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2fe7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2fe7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2fe7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2fe7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2fe7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2fe7-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2fe7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
