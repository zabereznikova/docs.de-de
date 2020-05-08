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
ms.openlocfilehash: 82f282630a2e31b8c67d43fa0f0b30431a0d6ee4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895061"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="ec39e-102">ICorDebugArrayValue::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="ec39e-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="ec39e-103">Ruft die Gesamtzahl der Elemente im Array ab.</span><span class="sxs-lookup"><span data-stu-id="ec39e-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec39e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec39e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec39e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec39e-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="ec39e-106">vorgenommen Ein Zeiger auf die Gesamtzahl der Elemente im Array.</span><span class="sxs-lookup"><span data-stu-id="ec39e-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec39e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec39e-107">Requirements</span></span>  
 <span data-ttu-id="ec39e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec39e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec39e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec39e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec39e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec39e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec39e-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec39e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
