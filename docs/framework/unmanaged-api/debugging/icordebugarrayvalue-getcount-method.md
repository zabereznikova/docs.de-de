---
title: ICorDebugArrayValue::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
ms.openlocfilehash: cd45c6d515648819a83d4e9944eb20d5cd20dd86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698220"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="5cf81-102">ICorDebugArrayValue::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5cf81-102">ICorDebugArrayValue::GetCount Method</span></span>

<span data-ttu-id="5cf81-103">Ruft die Gesamtzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="5cf81-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cf81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cf81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5cf81-105">Parameters</span></span>  

 `pnCount`  
 <span data-ttu-id="5cf81-106">vorgenommen Ein Zeiger auf die Gesamtzahl der Elemente im Array.</span><span class="sxs-lookup"><span data-stu-id="5cf81-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cf81-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5cf81-107">Requirements</span></span>  

 <span data-ttu-id="5cf81-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cf81-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf81-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cf81-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cf81-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cf81-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cf81-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf81-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
