---
title: ICorDebugChain::GetCallee-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744983"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="92ac2-102">ICorDebugChain::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="92ac2-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="92ac2-103">Ruft die Zertifikatskette, die von dieser Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="92ac2-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ac2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92ac2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ac2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92ac2-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="92ac2-106">[out] Ein Zeiger auf die Adresse des ICorDebugChain-Objekts, das die aufgerufene Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="92ac2-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="92ac2-107">Wenn diese Kette zurzeit ausgeführt wird (d.h., wenn dieser Kette nicht für eine aufgerufene Kette zurückzugebenden wartet), `ppChain` NULL.</span><span class="sxs-lookup"><span data-stu-id="92ac2-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92ac2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92ac2-108">Remarks</span></span>  
 <span data-ttu-id="92ac2-109">Diese Kette wird gewartet, für die aufgerufene Kette zurückgegeben wird, bevor sie die Ausführung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="92ac2-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="92ac2-110">Die aufgerufene Kette möglicherweise auf einem anderen Thread im Fall von threadübergreifende gemarshallte Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="92ac2-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ac2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92ac2-111">Requirements</span></span>  
 <span data-ttu-id="92ac2-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92ac2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ac2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ac2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ac2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ac2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ac2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ac2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
