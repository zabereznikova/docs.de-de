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
ms.openlocfilehash: c28ff84b08802246d587bfa130ae5915177932ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764308"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="e678b-102">ICorDebugValue2::GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="e678b-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="e678b-103">Ruft einen Schnittstellenzeiger auf ein "ICorDebugType"-Objekt, das darstellt ab der <xref:System.Type> dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="e678b-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e678b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e678b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e678b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e678b-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="e678b-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das darstellt der <xref:System.Type> des Werts von diesem Objekt "ICorDebugValue2" dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e678b-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e678b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e678b-107">Remarks</span></span>  
 <span data-ttu-id="e678b-108">Die Generika-bewusste `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) und [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) Methoden aller Informationen über den Typ eines Werts zurückgeben .</span><span class="sxs-lookup"><span data-stu-id="e678b-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e678b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e678b-109">Requirements</span></span>  
 <span data-ttu-id="e678b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e678b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e678b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e678b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e678b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e678b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e678b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e678b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e678b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e678b-114">See also</span></span>
