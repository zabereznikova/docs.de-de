---
title: ICorDebugFunction::GetToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56c8eba49260eba9e3e0ca7e9ab4c7cfcd3261f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995630"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="2a40d-102">ICorDebugFunction::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="2a40d-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="2a40d-103">Ruft den Metadatentoken für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="2a40d-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a40d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a40d-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a40d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a40d-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="2a40d-106">[out] Ein Zeiger auf ein `mdMethodDef` Token, die Metadaten für diese Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="2a40d-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a40d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a40d-107">Requirements</span></span>  
 <span data-ttu-id="2a40d-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a40d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a40d-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a40d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a40d-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a40d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a40d-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a40d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
