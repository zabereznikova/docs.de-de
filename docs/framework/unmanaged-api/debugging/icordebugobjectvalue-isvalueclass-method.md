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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 932d4ecbf34a636d37a60af0ba11f3fc149ffcea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649647"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="091bf-102">ICorDebugObjectValue::IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="091bf-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="091bf-103">Ruft einen Wert, der angibt, ob der Wert dieses Objekts ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="091bf-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="091bf-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="091bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="091bf-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="091bf-106">[out] Ein Zeiger auf einen booleschen Wert, der `true` der Objektwert, der von diesem "ICorDebugObjectValue" dargestellten ist ein Werttyp, anstatt einen Verweistyp handelt; andernfalls `pbIsValueClass` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="091bf-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091bf-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="091bf-107">Requirements</span></span>  
 <span data-ttu-id="091bf-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="091bf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091bf-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="091bf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="091bf-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="091bf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="091bf-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="091bf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091bf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="091bf-112">See also</span></span>


