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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481559"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="07d1e-102">ICorDebugChain::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="07d1e-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="07d1e-103">Ruft den Adressbereich des Stack-Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="07d1e-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d1e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07d1e-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07d1e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07d1e-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="07d1e-106">[out] Ein Zeiger auf eine `CORDB_ADDRESS` Wert, der die Startadresse des Stack-Segments.</span><span class="sxs-lookup"><span data-stu-id="07d1e-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="07d1e-107">[out] Ein Zeiger auf eine `CORDB_ADDRESS` Wert, der die Endadresse des Stack-Segments.</span><span class="sxs-lookup"><span data-stu-id="07d1e-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07d1e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07d1e-108">Remarks</span></span>  
 <span data-ttu-id="07d1e-109">Der numerische Bereich ist nur für den Vergleich der Stack-Frame-Standorte von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="07d1e-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="07d1e-110">Sie können keine Annahmen über was tatsächlich auf dem Stapel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="07d1e-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d1e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07d1e-111">Requirements</span></span>  
 <span data-ttu-id="07d1e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07d1e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d1e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07d1e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07d1e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07d1e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07d1e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d1e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
