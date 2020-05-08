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
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894692"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="0708d-102">ICorDebugChain::EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="0708d-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="0708d-103">Ruft einen Enumerator ab, der alle verwalteten Stapel Rahmen in der Kette enthält, beginnend mit dem letzten Frame.</span><span class="sxs-lookup"><span data-stu-id="0708d-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0708d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0708d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0708d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0708d-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="0708d-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das der Enumerator für die Stapel Rahmen ist.</span><span class="sxs-lookup"><span data-stu-id="0708d-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0708d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0708d-107">Remarks</span></span>  
 <span data-ttu-id="0708d-108">Die Kette stellt die physische aufrufsstapel für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="0708d-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="0708d-109">Die `EnumerateFrames` -Methode sollte nur für verwaltete Ketten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0708d-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="0708d-110">Die Debug-API stellt keine Methoden zum Abrufen von Frames bereit, die in nicht verwalteten Ketten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0708d-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="0708d-111">Der Debugger muss andere Mittel zum Abrufen dieser Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0708d-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0708d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0708d-112">Requirements</span></span>  
 <span data-ttu-id="0708d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0708d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0708d-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0708d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0708d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0708d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0708d-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0708d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
