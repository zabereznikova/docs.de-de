---
title: ICorDebugType::GetFirstTypeParameter-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3031cf2d9509f94b50c386b44e6d9e5d9ee5509c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768224"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="cc43a-102">ICorDebugType::GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="cc43a-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="cc43a-103">Ruft einen Schnittstellenzeiger auf ICorDebugType ab, der der erste gibt <xref:System.Type> Parameter des Typs dargestellt durch diese `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cc43a-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc43a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc43a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc43a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc43a-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="cc43a-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugType` Objekt, das den ersten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="cc43a-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc43a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc43a-107">Remarks</span></span>  
 <span data-ttu-id="cc43a-108">`GetFirstTypeParameter` kann aufgerufen werden in Fällen, in denen die zusätzliche Informationen über den Typ, höchstens umfasst, einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="cc43a-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="cc43a-109">Insbesondere, es kann verwendet werden, wenn der Typ ein ELEMENT_TYPE_ARRAY ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR, durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="cc43a-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc43a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cc43a-110">Requirements</span></span>  
 <span data-ttu-id="cc43a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc43a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc43a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc43a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc43a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc43a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc43a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc43a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
