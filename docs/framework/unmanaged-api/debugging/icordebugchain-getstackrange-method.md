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
ms.openlocfilehash: 8a6db1990df2ed6b29d548c147ed40b5bc98254d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745687"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="79ec5-102">ICorDebugChain::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="79ec5-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="79ec5-103">Ruft den Adressbereich des Stack-Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="79ec5-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ec5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79ec5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79ec5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="79ec5-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="79ec5-106">[out] Ein Zeiger auf eine `CORDB_ADDRESS` Wert, der die Startadresse des Stack-Segments.</span><span class="sxs-lookup"><span data-stu-id="79ec5-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="79ec5-107">[out] Ein Zeiger auf eine `CORDB_ADDRESS` Wert, der die Endadresse des Stack-Segments.</span><span class="sxs-lookup"><span data-stu-id="79ec5-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79ec5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79ec5-108">Remarks</span></span>  
 <span data-ttu-id="79ec5-109">Der numerische Bereich ist nur für den Vergleich der Stack-Frame-Standorte von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="79ec5-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="79ec5-110">Sie können keine Annahmen über was tatsächlich auf dem Stapel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="79ec5-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79ec5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79ec5-111">Requirements</span></span>  
 <span data-ttu-id="79ec5-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79ec5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79ec5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79ec5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79ec5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79ec5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79ec5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79ec5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
