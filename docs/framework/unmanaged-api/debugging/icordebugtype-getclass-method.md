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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff2258faa8bc766c8c769f4e135f868334516b96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422558"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="eff77-102">ICorDebugType::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="eff77-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="eff77-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugClass, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="eff77-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eff77-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eff77-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eff77-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="eff77-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugClass` Schnittstelle, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="eff77-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eff77-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eff77-107">Remarks</span></span>  
 <span data-ttu-id="eff77-108">`GetClass` kann nur unter bestimmten Umständen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="eff77-109">Rufen Sie [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) vor dem Aufruf `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="eff77-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="eff77-110">Wenn `ICorDebugType::GetType` einen CorElementType-Wert, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE lautet, gibt `GetClass` aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ abzurufen.</span><span class="sxs-lookup"><span data-stu-id="eff77-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eff77-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eff77-111">Requirements</span></span>  
 <span data-ttu-id="eff77-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eff77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eff77-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eff77-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eff77-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eff77-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eff77-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eff77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
