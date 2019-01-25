---
title: ICorDebugValue2::GetExactType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982af81f8f3886ae26b56114cc36374279c07593
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656348"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="45801-102">ICorDebugValue2::GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="45801-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="45801-103">Ruft einen Schnittstellenzeiger auf ein "ICorDebugType"-Objekt, das darstellt ab der <xref:System.Type> dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="45801-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45801-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45801-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45801-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45801-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="45801-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das darstellt der <xref:System.Type> des Werts von diesem Objekt "ICorDebugValue2" dargestellt.</span><span class="sxs-lookup"><span data-stu-id="45801-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45801-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45801-107">Remarks</span></span>  
 <span data-ttu-id="45801-108">Die Generika-bewusste `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) und [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) Methoden aller Informationen über den Typ eines Werts zurückgeben .</span><span class="sxs-lookup"><span data-stu-id="45801-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45801-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45801-109">Requirements</span></span>  
 <span data-ttu-id="45801-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45801-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45801-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45801-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45801-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45801-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45801-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45801-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45801-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45801-114">See also</span></span>

