---
title: ICorDebugChain::EnumerateFrames-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="e9179-102">ICorDebugChain::EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="e9179-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="e9179-103">Ruft ein Enumerator, der alle verwalteten Stapelrahmen in der Kette enthält, beginnend mit den aktuellsten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="e9179-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9179-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9179-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9179-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9179-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="e9179-106">[out] Ein Zeiger auf die Adresse eines ICorDebugFrameEnum-Objekts, das den Enumerator für Stapelrahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e9179-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9179-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9179-107">Remarks</span></span>  
 <span data-ttu-id="e9179-108">Die Kette stellt die physische Aufrufliste für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="e9179-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="e9179-109">Die `EnumerateFrames` Methode sollte nur für verwaltete Ketten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e9179-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="e9179-110">Die Debug-API stellt keine Methoden zum Abrufen von Frames, die in nicht verwalteten Ketten bereit.</span><span class="sxs-lookup"><span data-stu-id="e9179-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="e9179-111">Der Debugger muss auf andere Weise verwenden, um diese Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e9179-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9179-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9179-112">Requirements</span></span>  
 <span data-ttu-id="e9179-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9179-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9179-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9179-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9179-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9179-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9179-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9179-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
