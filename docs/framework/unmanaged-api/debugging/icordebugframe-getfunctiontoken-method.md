---
title: ICorDebugFrame::GetFunctionToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetFunctionToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7a3e4300c32a32fd76f253d34581f53e4afd95e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="b4c06-102">ICorDebugFrame::GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b4c06-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="b4c06-103">Ruft das Metadatentoken für die Funktion mit dem Code zugeordneten dieses Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="b4c06-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c06-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4c06-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4c06-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4c06-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="b4c06-106">[out] Ein Zeiger auf ein `mdMethodDef` Token, das die Metadaten für die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="b4c06-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c06-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4c06-107">Requirements</span></span>  
 <span data-ttu-id="b4c06-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c06-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c06-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4c06-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4c06-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4c06-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4c06-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c06-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
