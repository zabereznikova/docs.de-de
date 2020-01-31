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
ms.openlocfilehash: d15938e94d647fd5fded23c72bdc200d198d21a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792701"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="c3dfb-102">ICorDebugObjectValue::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="c3dfb-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="c3dfb-103">Ruft die Klasse dieses Objekt Werts ab.</span><span class="sxs-lookup"><span data-stu-id="c3dfb-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3dfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3dfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3dfb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c3dfb-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="c3dfb-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die Klasse des Objekt Werts darstellt, der durch dieses "ICorDebugObjectValue"-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c3dfb-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3dfb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3dfb-107">Remarks</span></span>  
 <span data-ttu-id="c3dfb-108">Die `GetClass`-Methode und die [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) -Methode geben alle Informationen zum Typ eines Werts zurück. Beide werden durch den Generics-fähigen [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md)ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c3dfb-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3dfb-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3dfb-109">Requirements</span></span>  
 <span data-ttu-id="c3dfb-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3dfb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3dfb-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3dfb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3dfb-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3dfb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3dfb-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3dfb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3dfb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3dfb-114">See also</span></span>
