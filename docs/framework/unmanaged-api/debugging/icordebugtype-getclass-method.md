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
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791297"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="82fb1-102">ICorDebugType::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="82fb1-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="82fb1-103">Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="82fb1-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82fb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82fb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82fb1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="82fb1-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="82fb1-106">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugClass`-Schnittstelle, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="82fb1-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82fb1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82fb1-107">Remarks</span></span>  
 <span data-ttu-id="82fb1-108">`GetClass` können nur unter bestimmten Bedingungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="82fb1-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="82fb1-109">Rufen Sie [ICorDebugType:: GetType](icordebugtype-gettype-method.md) auf, bevor Sie `GetClass`aufrufen.</span><span class="sxs-lookup"><span data-stu-id="82fb1-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="82fb1-110">Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, können `GetClass` aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="82fb1-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82fb1-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82fb1-111">Requirements</span></span>  
 <span data-ttu-id="82fb1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82fb1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82fb1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82fb1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82fb1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82fb1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82fb1-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82fb1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
