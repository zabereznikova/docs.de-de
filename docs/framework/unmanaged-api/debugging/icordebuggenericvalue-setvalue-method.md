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
ms.openlocfilehash: 493793c45e7d13511e4c36fe76e472a856b50d72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705747"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="27689-102">ICorDebugGenericValue::SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="27689-102">ICorDebugGenericValue::SetValue Method</span></span>

<span data-ttu-id="27689-103">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="27689-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27689-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27689-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27689-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27689-105">Parameters</span></span>  

 `pFrom`  
 <span data-ttu-id="27689-106">in Ein Zeiger auf den Puffer, aus dem der Wert kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="27689-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27689-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27689-107">Remarks</span></span>  

 <span data-ttu-id="27689-108">Bei Verweis Typen ist der Wert der Verweis und nicht der Inhalt.</span><span class="sxs-lookup"><span data-stu-id="27689-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27689-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="27689-109">Requirements</span></span>  

 <span data-ttu-id="27689-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27689-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27689-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27689-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27689-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27689-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27689-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27689-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
