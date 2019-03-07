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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be7eaeccb53e8b180aeb9492cd887f952bbaea5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485303"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="c9b2d-102">ICorDebugArrayValue::GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="c9b2d-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="c9b2d-103">Ruft den Wert des angegebenen Array-Elements.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9b2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9b2d-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9b2d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9b2d-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="c9b2d-106">[in] Die Anzahl der Dimensionen dieses `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="c9b2d-107">Dieser Wert ist auch die Größe der `indices` Arrays, da seine Größe gleich der Anzahl der Dimensionen ist die `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="c9b2d-108">[in] Ein Array der Indexwerte, von denen jeder eine Position innerhalb einer Dimension gibt den `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="c9b2d-109">Dieser Wert darf nicht null sein.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c9b2d-110">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des angegebenen Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9b2d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9b2d-111">Requirements</span></span>  
 <span data-ttu-id="c9b2d-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9b2d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9b2d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9b2d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9b2d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9b2d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9b2d-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9b2d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
