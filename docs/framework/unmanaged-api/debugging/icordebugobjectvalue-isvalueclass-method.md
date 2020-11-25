---
title: ICorDebugObjectValue::IsValueClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
ms.openlocfilehash: 7b637889986425767fd7e1166c73df3301075422
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695282"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="6db75-102">ICorDebugObjectValue::IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="6db75-102">ICorDebugObjectValue::IsValueClass Method</span></span>

<span data-ttu-id="6db75-103">Ruft einen Wert ab, der angibt, ob dieser Objektwert ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="6db75-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6db75-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6db75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6db75-105">Parameters</span></span>  

 `pbIsValueClass`  
 <span data-ttu-id="6db75-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn der Objektwert, der durch diesen "ICorDebugObjectValue" dargestellt wird, ein Werttyp anstelle eines Verweis Typs ist; andernfalls ist der Wert `pbIsValueClass` `false` .</span><span class="sxs-lookup"><span data-stu-id="6db75-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6db75-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6db75-107">Requirements</span></span>  

 <span data-ttu-id="6db75-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6db75-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6db75-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6db75-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6db75-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6db75-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6db75-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6db75-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db75-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6db75-112">See also</span></span>
