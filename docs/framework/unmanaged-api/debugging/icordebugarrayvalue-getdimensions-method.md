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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52075f33d594787c516f84b65b3319991380907
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645694"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="08df3-102">ICorDebugArrayValue::GetDimensions-Methode</span><span class="sxs-lookup"><span data-stu-id="08df3-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="08df3-103">Ruft die Anzahl der Elemente in jeder Dimension dieses Array ab.</span><span class="sxs-lookup"><span data-stu-id="08df3-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08df3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08df3-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08df3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08df3-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="08df3-106">[in] Die Anzahl der Dimensionen dieses ICorDebugArrayValue-Objekts.</span><span class="sxs-lookup"><span data-stu-id="08df3-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="08df3-107">Dieser Wert ist auch die Größe der `dims` Arrays, da seine Größe gleich der Anzahl der Dimensionen ist die `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="08df3-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="08df3-108">[out] Ein Array von Ganzzahlen, von denen jeder die Anzahl der Elemente in einer Dimension in diesem gibt `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="08df3-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08df3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08df3-109">Requirements</span></span>  
 <span data-ttu-id="08df3-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08df3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08df3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08df3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08df3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08df3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08df3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08df3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
