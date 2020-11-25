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
ms.openlocfilehash: 0b6b6f46c7fff8f1d4c2ad555c93423f9ca8ac09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698142"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="e3e47-102">ICorDebugArrayValue::GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="e3e47-102">ICorDebugArrayValue::GetElement Method</span></span>

<span data-ttu-id="e3e47-103">Ruft den Wert des angegebenen Array Elements ab.</span><span class="sxs-lookup"><span data-stu-id="e3e47-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3e47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3e47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3e47-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3e47-105">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="e3e47-106">in Die Anzahl der Dimensionen dieses `ICorDebugArrayValue` Objekts.</span><span class="sxs-lookup"><span data-stu-id="e3e47-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="e3e47-107">Dieser Wert ist auch die Größe des `indices` Arrays, da seine Größe gleich der Anzahl der Dimensionen des `ICorDebugArrayValue` Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="e3e47-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="e3e47-108">in Ein Array von Indexwerten, von denen jedes eine Position innerhalb einer Dimension des- `ICorDebugArrayValue` Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="e3e47-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="e3e47-109">Dieser Wert darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="e3e47-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e3e47-110">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den Wert des angegebenen Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3e47-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3e47-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e3e47-111">Requirements</span></span>  

 <span data-ttu-id="e3e47-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3e47-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3e47-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3e47-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3e47-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3e47-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3e47-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3e47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
