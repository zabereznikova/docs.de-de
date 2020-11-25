---
title: ICorDebugArrayValue::GetBaseIndicies-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: ea5c5a728afb9ac90f8599c833caab11fd0c65fe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731461"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="ba175-102">ICorDebugArrayValue::GetBaseIndicies-Methode</span><span class="sxs-lookup"><span data-stu-id="ba175-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>

<span data-ttu-id="ba175-103">Ruft den Basis Index jeder Dimension im Array ab.</span><span class="sxs-lookup"><span data-stu-id="ba175-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba175-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba175-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba175-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba175-105">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="ba175-106">in Die Anzahl der Dimensionen dieses `ICorDebugArrayValue` Objekts.</span><span class="sxs-lookup"><span data-stu-id="ba175-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="ba175-107">Dieser Wert ist auch die Größe des `indicies` Arrays, da seine Größe gleich der Anzahl der Dimensionen des `ICorDebugArrayValue` Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="ba175-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="ba175-108">vorgenommen Ein Array von ganzen Zahlen, von denen jeder der Basis Index (d. h. der Start Index) einer Dimension dieses Objekts ist `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="ba175-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba175-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ba175-109">Requirements</span></span>  

 <span data-ttu-id="ba175-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba175-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba175-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba175-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba175-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba175-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba175-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba175-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
