---
title: ICorDebugGenericValue::SetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6907cdf78fc70c75ddd711cd8593427857b172
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756893"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="a0193-102">ICorDebugGenericValue::SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a0193-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="a0193-103">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="a0193-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0193-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0193-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0193-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0193-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="a0193-106">[in] Ein Zeiger auf den Puffer, aus dem den Wert kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a0193-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0193-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0193-107">Remarks</span></span>  
 <span data-ttu-id="a0193-108">Für Verweistypen ist der Wert für den Verweis, nicht den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a0193-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0193-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0193-109">Requirements</span></span>  
 <span data-ttu-id="a0193-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0193-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0193-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0193-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0193-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0193-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0193-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0193-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
