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
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894453"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="3345c-102">ICorDebugChain::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="3345c-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="3345c-103">Ruft den Adressbereich des Stapel Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="3345c-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3345c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3345c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3345c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3345c-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="3345c-106">vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` -Wert, der die Startadresse des Stapel Segments ist.</span><span class="sxs-lookup"><span data-stu-id="3345c-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="3345c-107">vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` -Wert, der die Endadresse des Stapel Segments ist.</span><span class="sxs-lookup"><span data-stu-id="3345c-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3345c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3345c-108">Remarks</span></span>  
 <span data-ttu-id="3345c-109">Der numerische Bereich ist nur für den Vergleich von Stapel Rahmen Positionen sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="3345c-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="3345c-110">Sie können keine Annahmen darüber treffen, was tatsächlich im Stapel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="3345c-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3345c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3345c-111">Requirements</span></span>  
 <span data-ttu-id="3345c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3345c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3345c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3345c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3345c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3345c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3345c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3345c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
