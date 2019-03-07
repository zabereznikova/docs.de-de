---
title: ICorDebugEval::IsActive-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d992ea86b3221af222bb01f1985fe277cea5a2c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480051"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="8cad5-102">ICorDebugEval::IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="8cad5-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="8cad5-103">Ruft einen Wert, der angibt, ob dieses ICorDebugEval Objekt gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8cad5-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cad5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cad5-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cad5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8cad5-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="8cad5-106">[out] Zeiger auf einen Wert, der angibt, ob diese Auswertung aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="8cad5-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cad5-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8cad5-107">Requirements</span></span>  
 <span data-ttu-id="8cad5-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cad5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cad5-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cad5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cad5-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cad5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cad5-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cad5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
