---
title: ICorDebugArrayValue::GetDimensions-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: c5199794098e4d83588728eeb165aee5f81fe4c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088501"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="44f95-102">ICorDebugArrayValue::GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="44f95-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="44f95-103">Ruft die Anzahl der Elemente in jeder Dimension dieses Arrays ab.</span><span class="sxs-lookup"><span data-stu-id="44f95-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44f95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f95-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44f95-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="44f95-106">in Die Anzahl der Dimensionen dieses ICorDebugArrayValue-Objekts.</span><span class="sxs-lookup"><span data-stu-id="44f95-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="44f95-107">Dieser Wert ist auch die Größe des `dims` Arrays, da seine Größe gleich der Anzahl der Dimensionen des `ICorDebugArrayValue` Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="44f95-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="44f95-108">vorgenommen Ein Array von ganzen Zahlen, von denen jede die Anzahl der Elemente in einer Dimension in diesem `ICorDebugArrayValue` Objekt angibt.</span><span class="sxs-lookup"><span data-stu-id="44f95-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f95-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44f95-109">Requirements</span></span>  
 <span data-ttu-id="44f95-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44f95-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f95-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44f95-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44f95-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44f95-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44f95-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
