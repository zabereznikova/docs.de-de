---
title: ICorDebugObjectValue::GetClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 42e5ffeeb81bc5e9a99c8ada8d58296fc9f610d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695399"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="63018-102">ICorDebugObjectValue::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="63018-102">ICorDebugObjectValue::GetClass Method</span></span>

<span data-ttu-id="63018-103">Ruft die Klasse dieses Objekt Werts ab.</span><span class="sxs-lookup"><span data-stu-id="63018-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63018-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63018-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63018-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63018-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="63018-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die Klasse des Objekt Werts darstellt, der durch dieses "ICorDebugObjectValue"-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="63018-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63018-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63018-107">Remarks</span></span>  

 <span data-ttu-id="63018-108">Die `GetClass` -Methode und die [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) -Methode geben jeweils Informationen über den Typ eines Werts zurück. beide werden durch den Generika-fähigen [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md)abgelöst.</span><span class="sxs-lookup"><span data-stu-id="63018-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63018-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="63018-109">Requirements</span></span>  

 <span data-ttu-id="63018-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63018-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63018-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63018-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63018-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63018-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63018-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63018-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63018-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63018-114">See also</span></span>
