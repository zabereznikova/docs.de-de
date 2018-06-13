---
title: ICorDebugCode::IsIL-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccebe01c853677f7c78731e757ef7a5f090d6919
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415190"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="7ac71-102">ICorDebugCode::IsIL-Methode</span><span class="sxs-lookup"><span data-stu-id="7ac71-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="7ac71-103">Ruft einen Wert, der angibt, ob "ICorDebugCode" darstellt, der in Microsoft intermediate Language (MSIL) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="7ac71-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac71-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ac71-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ac71-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ac71-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="7ac71-106">[out] `true` Wenn diese `ICorDebugCode` Code darstellt, der in MSIL kompilierte; andernfalls wurde `false`.</span><span class="sxs-lookup"><span data-stu-id="7ac71-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac71-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ac71-107">Requirements</span></span>  
 <span data-ttu-id="7ac71-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ac71-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac71-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ac71-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ac71-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ac71-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ac71-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac71-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac71-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ac71-112">See Also</span></span>  
 
