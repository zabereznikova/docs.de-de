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
ms.openlocfilehash: 9fddee70e34ba9bf7c1860c1a160db369e45fb5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698160"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="1a193-102">ICorDebugArrayValue::GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="1a193-102">ICorDebugArrayValue::GetRank Method</span></span>

<span data-ttu-id="1a193-103">Ruft die Anzahl der Dimensionen im Array ab.</span><span class="sxs-lookup"><span data-stu-id="1a193-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a193-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a193-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a193-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a193-105">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="1a193-106">vorgenommen Ein Zeiger auf die Anzahl der Dimensionen in diesem- `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1a193-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a193-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1a193-107">Requirements</span></span>  

 <span data-ttu-id="1a193-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a193-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a193-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a193-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a193-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a193-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a193-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a193-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
