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
ms.openlocfilehash: 99972c5840645c95b7b349daf2d8ea7173d0cc03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674723"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="6347b-102">ICorDebugCode::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="6347b-102">ICorDebugCode::GetFunction Method</span></span>

<span data-ttu-id="6347b-103">Ruft den "ICorDebugFunction" ab, der diesem "ICorDebugCode" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6347b-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6347b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6347b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6347b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6347b-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="6347b-106">vorgenommen Ein Zeiger auf die Adresse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6347b-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6347b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6347b-107">Remarks</span></span>  

 <span data-ttu-id="6347b-108">`ICorDebugCode` und `ICorDebugFunction` pflegen eine 1:1-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="6347b-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6347b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6347b-109">Requirements</span></span>  

 <span data-ttu-id="6347b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6347b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6347b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6347b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6347b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6347b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6347b-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6347b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
