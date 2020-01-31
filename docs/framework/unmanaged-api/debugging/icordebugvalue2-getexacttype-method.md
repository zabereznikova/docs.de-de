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
ms.openlocfilehash: 6c5e5d1c9f734e097fc9e871d7a0cffdc9bb9138
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791126"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="98299-102">ICorDebugValue2::GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="98299-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="98299-103">Ruft einen Schnittstellen Zeiger auf ein ICorDebugType-Objekt ab, das die <xref:System.Type> dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="98299-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98299-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98299-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98299-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="98299-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="98299-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das die <xref:System.Type> des Werts darstellt, der durch dieses "ICorDebugValue2"-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="98299-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98299-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98299-107">Remarks</span></span>  
 <span data-ttu-id="98299-108">Die Generika unterstützende `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) -Methode als auch die [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) -Methode, die jeweils Informationen über den Typ eines Werts zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="98299-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98299-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98299-109">Requirements</span></span>  
 <span data-ttu-id="98299-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98299-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98299-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98299-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98299-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98299-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98299-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98299-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98299-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98299-114">See also</span></span>
