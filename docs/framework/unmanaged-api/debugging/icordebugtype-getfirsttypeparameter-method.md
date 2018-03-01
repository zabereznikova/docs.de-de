---
title: ICorDebugType::GetFirstTypeParameter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e963553bfeac2d659de8fc460a938d2d523b53e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="0ace6-102">ICorDebugType::GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="0ace6-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="0ace6-103">Ruft einen Schnittstellenzeiger auf ICorDebugType ab, der die erste gibt <xref:System.Type> Parameter des Typs dargestellt, die von diesem `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="0ace6-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ace6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ace6-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ace6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ace6-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="0ace6-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das den ersten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ace6-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ace6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ace6-107">Remarks</span></span>  
 <span data-ttu-id="0ace6-108">`GetFirstTypeParameter`kann aufgerufen werden in Fällen, in dem die zusätzliche Informationen über die Art, höchstens umfasst, einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="0ace6-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="0ace6-109">Insbesondere, er kann verwendet werden, wenn der Typ ein einem ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR, ist durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0ace6-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ace6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ace6-110">Requirements</span></span>  
 <span data-ttu-id="0ace6-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ace6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ace6-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ace6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ace6-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ace6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ace6-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ace6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
