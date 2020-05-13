---
title: ICorDebugType::GetType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379923"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="acd12-102">ICorDebugType::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="acd12-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="acd12-103">Ruft einen korelementtype-Wert ab, der den systemeigenen Typ des Common Language Runtime (CLR) beschreibt, der <xref:System.Type> durch diesen ICorDebugType dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="acd12-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acd12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acd12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acd12-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="acd12-106">vorgenommen Ein Zeiger auf einen Wert der- `CorElementType` Enumeration, der die CLR angibt <xref:System.Type> , die dieser `ICorDebugType` darstellt.</span><span class="sxs-lookup"><span data-stu-id="acd12-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acd12-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acd12-107">Remarks</span></span>  
 <span data-ttu-id="acd12-108">Wenn der Wert von `ty` entweder ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, kann die [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) -Methode aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ abzurufen. andernfalls dürfen Sie nicht aufrufen `ICorDebugType::GetClass` .</span><span class="sxs-lookup"><span data-stu-id="acd12-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acd12-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="acd12-109">Requirements</span></span>  
 <span data-ttu-id="acd12-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acd12-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd12-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acd12-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acd12-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acd12-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acd12-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acd12-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
