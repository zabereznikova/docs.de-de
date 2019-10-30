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
ms.openlocfilehash: 217ca0a850926e5f697340cece264c6ed442a9bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125644"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="54e38-102">ICorDebugCode::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="54e38-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="54e38-103">Ruft den "ICorDebugFunction" ab, der diesem "ICorDebugCode" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="54e38-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54e38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54e38-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="54e38-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="54e38-106">vorgenommen Ein Zeiger auf die Adresse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="54e38-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54e38-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54e38-107">Remarks</span></span>  
 <span data-ttu-id="54e38-108">`ICorDebugCode` und `ICorDebugFunction` eine 1:1-Beziehung aufrechterhalten.</span><span class="sxs-lookup"><span data-stu-id="54e38-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e38-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="54e38-109">Requirements</span></span>  
 <span data-ttu-id="54e38-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e38-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e38-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54e38-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54e38-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54e38-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54e38-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e38-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
