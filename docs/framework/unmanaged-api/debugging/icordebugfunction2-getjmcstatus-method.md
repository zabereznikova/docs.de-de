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
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137816"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="f9e7b-102">ICorDebugFunction2::GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="f9e7b-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="f9e7b-103">Ruft einen Wert ab, der angibt, ob die Funktion, die durch dieses ICorDebugFunction2-Objekt dargestellt wird, als Benutzercode gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="f9e7b-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9e7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9e7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9e7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9e7b-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="f9e7b-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der `true`ist, wenn diese Funktion als Benutzercode markiert ist. Andernfalls ist der Wert `false`.</span><span class="sxs-lookup"><span data-stu-id="f9e7b-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9e7b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9e7b-107">Remarks</span></span>  
 <span data-ttu-id="f9e7b-108">Wenn die Funktion, die von diesem `ICorDebugFunction2` dargestellt wird, nicht deentschlbelt werden kann, werden `pbIsJustMyCode` immer `false`.</span><span class="sxs-lookup"><span data-stu-id="f9e7b-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9e7b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9e7b-109">Requirements</span></span>  
 <span data-ttu-id="f9e7b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9e7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9e7b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9e7b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9e7b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9e7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9e7b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9e7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
