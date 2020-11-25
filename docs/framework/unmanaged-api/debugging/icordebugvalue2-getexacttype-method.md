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
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720359"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="930e2-102">ICorDebugValue2::GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="930e2-102">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="930e2-103">Ruft einen Schnittstellen Zeiger auf ein ICorDebugType-Objekt ab, das den <xref:System.Type> dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="930e2-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="930e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="930e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="930e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="930e2-105">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="930e2-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das die des Werts darstellt, der <xref:System.Type> durch dieses "ICorDebugValue2"-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="930e2-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="930e2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="930e2-107">Remarks</span></span>  

 <span data-ttu-id="930e2-108">Die Generika-kompatible `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) -Methode als auch die [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) -Methode, die jeweils Informationen über den Typ eines Werts zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="930e2-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="930e2-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="930e2-109">Requirements</span></span>  

 <span data-ttu-id="930e2-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="930e2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="930e2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="930e2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="930e2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="930e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="930e2-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="930e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930e2-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="930e2-114">See also</span></span>
