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
ms.openlocfilehash: 7568f8ca3b92ef465ab595348f68895f389d61e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489708"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="4c125-102">ICorDebugChain::EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="4c125-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="4c125-103">Ruft einen Enumerator, der alle verwalteten Stapelrahmen in der Kette, enthält der letzten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="4c125-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c125-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c125-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c125-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c125-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="4c125-106">[out] Ein Zeiger auf die Adresse des ICorDebugFrameEnum-Objekts, das den Enumerator für Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="4c125-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c125-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c125-107">Remarks</span></span>  
 <span data-ttu-id="4c125-108">Die Kette stellt die physische Aufrufliste für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="4c125-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="4c125-109">Die `EnumerateFrames` -Methode nur für verwaltete Ketten aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c125-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="4c125-110">Die Debug-API bietet keine Methoden zum Abrufen von Frames, die in nicht verwalteten Ketten.</span><span class="sxs-lookup"><span data-stu-id="4c125-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="4c125-111">Der Debugger muss anderweitig verwenden, um diese Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4c125-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c125-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c125-112">Requirements</span></span>  
 <span data-ttu-id="4c125-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c125-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c125-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c125-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c125-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c125-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c125-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c125-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
