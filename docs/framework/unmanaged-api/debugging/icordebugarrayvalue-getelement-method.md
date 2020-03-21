---
title: ICorDebugArrayValue::GetElement-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: adcb7b5a27f3b8c63dbbb660a23b5c891f84ac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179007"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="c948f-102">ICorDebugArrayValue::GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="c948f-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="c948f-103">Ruft den Wert des angegebenen Arrayelements ab.</span><span class="sxs-lookup"><span data-stu-id="c948f-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c948f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c948f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c948f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c948f-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="c948f-106">[in] Die Anzahl der `ICorDebugArrayValue` Dimensionen dieses Objekts.</span><span class="sxs-lookup"><span data-stu-id="c948f-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="c948f-107">Dieser Wert ist auch `indices` die Größe des Arrays, da seine `ICorDebugArrayValue` Größe der Anzahl der Dimensionen des Objekts entspricht.</span><span class="sxs-lookup"><span data-stu-id="c948f-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="c948f-108">[in] Ein Array von Indexwerten, von denen jeder eine `ICorDebugArrayValue` Position innerhalb einer Dimension des Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="c948f-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="c948f-109">Dieser Wert darf nicht null sein.</span><span class="sxs-lookup"><span data-stu-id="c948f-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c948f-110">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des angegebenen Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="c948f-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c948f-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c948f-111">Requirements</span></span>  
 <span data-ttu-id="c948f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c948f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c948f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c948f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c948f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c948f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c948f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c948f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
