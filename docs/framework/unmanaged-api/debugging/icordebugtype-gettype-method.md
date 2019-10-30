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
ms.openlocfilehash: 7f3010cccc584288608b3f6ba95efbeb95f271fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132063"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="e9ed3-102">ICorDebugType::GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="e9ed3-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="e9ed3-103">Ruft einen korelementtype-Wert ab, der den systemeigenen Typ des von diesem ICorDebugType dargestellten Common Language Runtime (CLR) <xref:System.Type> beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e9ed3-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9ed3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9ed3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9ed3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9ed3-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="e9ed3-106">vorgenommen Ein Zeiger auf einen Wert der `CorElementType`-Enumeration, die die CLR-<xref:System.Type> angibt, die dieser `ICorDebugType` darstellt.</span><span class="sxs-lookup"><span data-stu-id="e9ed3-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9ed3-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9ed3-107">Remarks</span></span>  
 <span data-ttu-id="e9ed3-108">Wenn der Wert `ty` entweder "ELEMENT_TYPE_CLASS" oder "ELEMENT_TYPE_VALUETYPE" ist, kann die [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) -Methode aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten. Andernfalls sollten Sie `ICorDebugType::GetClass`nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e9ed3-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9ed3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9ed3-109">Requirements</span></span>  
 <span data-ttu-id="e9ed3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9ed3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ed3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9ed3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9ed3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9ed3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9ed3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ed3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
