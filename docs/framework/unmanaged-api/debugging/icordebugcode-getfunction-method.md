---
title: ICorDebugCode::GetFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8d0e7f20be3f18e49dcc1b986460d5da0c3d7777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401939"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="b74be-102">ICorDebugCode::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="b74be-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="b74be-103">Ruft die "ICorDebugCode" zugeordnet "ICorDebugFunction" ab.</span><span class="sxs-lookup"><span data-stu-id="b74be-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b74be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b74be-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b74be-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b74be-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="b74be-106">[out] Ein Zeiger auf die Adresse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="b74be-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b74be-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b74be-107">Remarks</span></span>  
 <span data-ttu-id="b74be-108">`ICorDebugCode` und `ICorDebugFunction` : 1-Beziehung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b74be-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b74be-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b74be-109">Requirements</span></span>  
 <span data-ttu-id="b74be-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b74be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b74be-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b74be-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b74be-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b74be-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b74be-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b74be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74be-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b74be-114">See Also</span></span>  
 
