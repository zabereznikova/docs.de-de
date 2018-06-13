---
title: ICorDebugArrayValue::GetRank-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdac5bc1d205184771388b13e9b5380ff42bfba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401926"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="9c612-102">ICorDebugArrayValue::GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="9c612-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="9c612-103">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="9c612-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c612-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c612-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c612-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c612-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="9c612-106">[out] Ein Zeiger auf die Anzahl der Dimensionen in diesem `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="9c612-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c612-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c612-107">Requirements</span></span>  
 <span data-ttu-id="9c612-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c612-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c612-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c612-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c612-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c612-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c612-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c612-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
