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
ms.openlocfilehash: d408f317b546fb7e8314e904e6f5ad9e6296ae6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403265"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="152ce-102">ICorDebugChain::EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="152ce-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="152ce-103">Ruft ein Enumerator, der alle verwalteten Stapelrahmen in der Kette enthält, beginnend mit den aktuellsten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="152ce-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="152ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="152ce-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="152ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="152ce-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="152ce-106">[out] Ein Zeiger auf die Adresse eines ICorDebugFrameEnum-Objekts, das den Enumerator für Stapelrahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="152ce-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="152ce-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="152ce-107">Remarks</span></span>  
 <span data-ttu-id="152ce-108">Die Kette stellt die physische Aufrufliste für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="152ce-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="152ce-109">Die `EnumerateFrames` Methode sollte nur für verwaltete Ketten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="152ce-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="152ce-110">Die Debug-API stellt keine Methoden zum Abrufen von Frames, die in nicht verwalteten Ketten bereit.</span><span class="sxs-lookup"><span data-stu-id="152ce-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="152ce-111">Der Debugger muss auf andere Weise verwenden, um diese Informationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="152ce-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="152ce-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="152ce-112">Requirements</span></span>  
 <span data-ttu-id="152ce-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="152ce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="152ce-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="152ce-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="152ce-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="152ce-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="152ce-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="152ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
