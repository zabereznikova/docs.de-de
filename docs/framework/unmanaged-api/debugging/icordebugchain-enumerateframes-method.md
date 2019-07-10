---
title: ICorDebugChain::EnumerateFrames-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc647805fcb7d8354a2540ac9424dc7155853444
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745031"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="c55e8-102">ICorDebugChain::EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="c55e8-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="c55e8-103">Ruft einen Enumerator, der alle verwalteten Stapelrahmen in der Kette, enthält der letzten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="c55e8-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c55e8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c55e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c55e8-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="c55e8-106">[out] Ein Zeiger auf die Adresse des ICorDebugFrameEnum-Objekts, das den Enumerator für Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="c55e8-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c55e8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c55e8-107">Remarks</span></span>  
 <span data-ttu-id="c55e8-108">Die Kette stellt die physische Aufrufliste für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="c55e8-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="c55e8-109">Die `EnumerateFrames` -Methode nur für verwaltete Ketten aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c55e8-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="c55e8-110">Die Debug-API bietet keine Methoden zum Abrufen von Frames, die in nicht verwalteten Ketten.</span><span class="sxs-lookup"><span data-stu-id="c55e8-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="c55e8-111">Der Debugger muss anderweitig verwenden, um diese Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c55e8-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55e8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c55e8-112">Requirements</span></span>  
 <span data-ttu-id="c55e8-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c55e8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c55e8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c55e8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c55e8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c55e8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c55e8-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c55e8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
