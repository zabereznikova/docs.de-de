---
title: ICorDebugObjectValue::GetClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d403fe24f368a5cd05358cd589023a4c8710a37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587419"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="a1547-102">ICorDebugObjectValue::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="a1547-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="a1547-103">Ruft die Klasse, der Wert dieses Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="a1547-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1547-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1547-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1547-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1547-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="a1547-106">[out] Ein Zeiger auf die Adresse ein "ICorDebugClass"-Objekt, das die Klasse des Objektwerts dargestellt, die von diesem Objekt "ICorDebugObjectValue" darstellt.</span><span class="sxs-lookup"><span data-stu-id="a1547-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1547-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1547-107">Remarks</span></span>  
 <span data-ttu-id="a1547-108">Die `GetClass` und [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) -Methode geben Informationen über den Typ eines Werts; sie werden beide ersetzt, durch die Generika-bewusste [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1547-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1547-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1547-109">Requirements</span></span>  
 <span data-ttu-id="a1547-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1547-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1547-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1547-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1547-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1547-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1547-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1547-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1547-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1547-114">See also</span></span>


