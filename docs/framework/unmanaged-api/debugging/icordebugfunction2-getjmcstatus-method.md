---
title: ICorDebugFunction2::GetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 747f165a98dfd1264ea58d61aaa1615c6d71e073
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726291"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="2ba44-102">ICorDebugFunction2::GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="2ba44-102">ICorDebugFunction2::GetJMCStatus Method</span></span>

<span data-ttu-id="2ba44-103">Ruft einen Wert ab, der angibt, ob die Funktion, die durch dieses ICorDebugFunction2-Objekt dargestellt wird, als Benutzercode gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="2ba44-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ba44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ba44-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ba44-105">Parameters</span></span>  

 `pbIsJustMyCode`  
 <span data-ttu-id="2ba44-106">vorgenommen Ein Zeiger auf einen booleschen Wert `true` , der ist, wenn diese Funktion als Benutzercode gekennzeichnet ist, andernfalls ist der Wert `false` .</span><span class="sxs-lookup"><span data-stu-id="2ba44-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ba44-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ba44-107">Remarks</span></span>  

 <span data-ttu-id="2ba44-108">Wenn die Funktion, die von diesem dargestellt `ICorDebugFunction2` wird, nicht deentschlbelt werden kann, ist `pbIsJustMyCode` immer `false` .</span><span class="sxs-lookup"><span data-stu-id="2ba44-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba44-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ba44-109">Requirements</span></span>  

 <span data-ttu-id="2ba44-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ba44-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba44-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ba44-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ba44-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ba44-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ba44-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba44-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
