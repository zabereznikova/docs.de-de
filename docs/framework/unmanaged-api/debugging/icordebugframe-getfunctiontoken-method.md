---
title: ICorDebugFrame::GetFunctionToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50e5fcee3705e05aeed820cf736613c12b00e50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754871"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="9594f-102">ICorDebugFrame::GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="9594f-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="9594f-103">Ruft das Metadatentoken für die Funktion, die den Code für diesen Stapelrahmen enthält.</span><span class="sxs-lookup"><span data-stu-id="9594f-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9594f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9594f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9594f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9594f-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="9594f-106">[out] Ein Zeiger auf ein `mdMethodDef` Token, die Metadaten für die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="9594f-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9594f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9594f-107">Requirements</span></span>  
 <span data-ttu-id="9594f-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9594f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9594f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9594f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9594f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9594f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9594f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9594f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
