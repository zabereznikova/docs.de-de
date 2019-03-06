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
ms.openlocfilehash: 4d872e4a65c0556dddac468336e6a42dd7d7923c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477648"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="b753e-102">ICorDebugType::GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="b753e-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="b753e-103">Ruft einen Schnittstellenzeiger auf ICorDebugType ab, der der erste gibt <xref:System.Type> Parameter des Typs dargestellt durch diese `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b753e-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b753e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b753e-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b753e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b753e-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="b753e-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugType` Objekt, das den ersten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="b753e-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b753e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b753e-107">Remarks</span></span>  
 <span data-ttu-id="b753e-108">`GetFirstTypeParameter` kann aufgerufen werden in Fällen, in denen die zusätzliche Informationen über den Typ, höchstens umfasst, einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="b753e-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="b753e-109">Insbesondere, es kann verwendet werden, wenn der Typ ein ELEMENT_TYPE_ARRAY ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR, durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b753e-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b753e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b753e-110">Requirements</span></span>  
 <span data-ttu-id="b753e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b753e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b753e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b753e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b753e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b753e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b753e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b753e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
