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
ms.openlocfilehash: 972a981188c36236b81f3da17c09abeeb1e32857
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212190"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="e81d2-102">ICorDebugGenericValue::SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e81d2-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="e81d2-103">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="e81d2-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e81d2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e81d2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e81d2-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="e81d2-106">in Ein Zeiger auf den Puffer, aus dem der Wert kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e81d2-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e81d2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e81d2-107">Remarks</span></span>  
 <span data-ttu-id="e81d2-108">Bei Verweis Typen ist der Wert der Verweis und nicht der Inhalt.</span><span class="sxs-lookup"><span data-stu-id="e81d2-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81d2-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e81d2-109">Requirements</span></span>  
 <span data-ttu-id="e81d2-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e81d2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81d2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e81d2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e81d2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e81d2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e81d2-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81d2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
