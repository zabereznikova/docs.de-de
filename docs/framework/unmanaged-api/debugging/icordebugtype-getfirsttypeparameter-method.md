---
title: ICorDebugType::GetFirstTypeParameter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetFirstTypeParameter
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 233d7165e73c2b568a1693eeab024380bc356d1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="d4d07-102">ICorDebugType::GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="d4d07-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="d4d07-103">Ruft einen Schnittstellenzeiger auf ICorDebugType ab, der die erste gibt <xref:System.Type> Parameter des Typs dargestellt, die von diesem `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="d4d07-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4d07-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4d07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4d07-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="d4d07-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das den ersten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="d4d07-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4d07-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4d07-107">Remarks</span></span>  
 <span data-ttu-id="d4d07-108">`GetFirstTypeParameter`kann aufgerufen werden in Fällen, in dem die zusätzliche Informationen über die Art, höchstens umfasst, einen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="d4d07-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="d4d07-109">Insbesondere, er kann verwendet werden, wenn der Typ ein einem ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR, ist durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d4d07-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d07-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4d07-110">Requirements</span></span>  
 <span data-ttu-id="d4d07-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4d07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4d07-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4d07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4d07-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4d07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4d07-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4d07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
