---
title: ICorDebugType::GetClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379961"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="beef7-102">ICorDebugType::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="beef7-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="beef7-103">Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="beef7-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beef7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="beef7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beef7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="beef7-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="beef7-106">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugClass` Schnittstelle, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="beef7-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beef7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="beef7-107">Remarks</span></span>  
 <span data-ttu-id="beef7-108">`GetClass`kann nur unter bestimmten Bedingungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="beef7-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="beef7-109">Rufen Sie [ICorDebugType:: GetType](icordebugtype-gettype-method.md) auf, bevor Sie aufrufen `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="beef7-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="beef7-110">Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, `GetClass` kann aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="beef7-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beef7-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="beef7-111">Requirements</span></span>  
 <span data-ttu-id="beef7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beef7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beef7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beef7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beef7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beef7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beef7-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beef7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
