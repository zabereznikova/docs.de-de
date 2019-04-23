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
ms.openlocfilehash: a82606d90444c2d543065287780e42da4f8b4943
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180686"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="f00ee-102">ICorDebugCode::IsIL-Methode</span><span class="sxs-lookup"><span data-stu-id="f00ee-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="f00ee-103">Ruft einen Wert, der angibt, ob "ICorDebugCode" Code darstellt, die in Microsoft intermediate Language (MSIL) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="f00ee-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f00ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f00ee-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f00ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f00ee-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="f00ee-106">[out] `true` Wenn diese `ICorDebugCode` Code darstellt, der wurde in MSIL kompilierte; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f00ee-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f00ee-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f00ee-107">Requirements</span></span>  
 <span data-ttu-id="f00ee-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f00ee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f00ee-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f00ee-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f00ee-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f00ee-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f00ee-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f00ee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00ee-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f00ee-112">See also</span></span>
