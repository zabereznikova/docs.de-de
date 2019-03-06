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
ms.openlocfilehash: 03d701d0801c55b6e91600f0767a6d737e4915c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479947"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="3ceb4-102">ICorDebugValue2::GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="3ceb4-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="3ceb4-103">Ruft einen Schnittstellenzeiger auf ein "ICorDebugType"-Objekt, das darstellt ab der <xref:System.Type> dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="3ceb4-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ceb4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ceb4-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ceb4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ceb4-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="3ceb4-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das darstellt der <xref:System.Type> des Werts von diesem Objekt "ICorDebugValue2" dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3ceb4-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ceb4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ceb4-107">Remarks</span></span>  
 <span data-ttu-id="3ceb4-108">Die Generika-bewusste `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) und [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) Methoden aller Informationen über den Typ eines Werts zurückgeben .</span><span class="sxs-lookup"><span data-stu-id="3ceb4-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ceb4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ceb4-109">Requirements</span></span>  
 <span data-ttu-id="3ceb4-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ceb4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ceb4-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ceb4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ceb4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ceb4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ceb4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ceb4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ceb4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ceb4-114">See also</span></span>

