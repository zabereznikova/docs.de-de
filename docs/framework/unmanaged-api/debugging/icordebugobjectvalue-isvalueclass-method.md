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
ms.openlocfilehash: 71e32211e6ab16fb5e4e2c624dbad3af5fd6b09f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132014"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="45877-102">ICorDebugObjectValue::IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="45877-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="45877-103">Ruft einen Wert, der angibt, ob der Wert dieses Objekts ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="45877-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45877-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45877-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45877-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45877-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="45877-106">[out] Ein Zeiger auf einen booleschen Wert, der `true` der Objektwert, der von diesem "ICorDebugObjectValue" dargestellten ist ein Werttyp, anstatt einen Verweistyp handelt; andernfalls `pbIsValueClass` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="45877-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45877-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45877-107">Requirements</span></span>  
 <span data-ttu-id="45877-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45877-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45877-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45877-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45877-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45877-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="45877-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="45877-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45877-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45877-112">See also</span></span>
