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
ms.openlocfilehash: 3bb4331b1c55cbda818866c5ff08f9bacd3ebae0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413984"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="23727-102">ICorDebugFrame::GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="23727-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="23727-103">Ruft das Metadatentoken für die Funktion mit dem Code zugeordneten dieses Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="23727-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23727-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23727-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23727-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23727-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="23727-106">[out] Ein Zeiger auf ein `mdMethodDef` Token, das die Metadaten für die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="23727-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23727-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23727-107">Requirements</span></span>  
 <span data-ttu-id="23727-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23727-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23727-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23727-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23727-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23727-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23727-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23727-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
