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
ms.openlocfilehash: 3a895f432ed640cc35a492df0c91cece34893062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122365"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="2c21b-102">ICorDebugType::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="2c21b-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="2c21b-103">Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="2c21b-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c21b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c21b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c21b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c21b-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="2c21b-106">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugClass`-Schnittstelle, die den nicht instanziierten generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="2c21b-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c21b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c21b-107">Remarks</span></span>  
 <span data-ttu-id="2c21b-108">`GetClass` können nur unter bestimmten Bedingungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2c21b-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="2c21b-109">Rufen Sie [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) auf, bevor Sie `GetClass`aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2c21b-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="2c21b-110">Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der "ELEMENT_TYPE_CLASS" oder "ELEMENT_TYPE_VALUETYPE" ist, können `GetClass` aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c21b-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c21b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c21b-111">Requirements</span></span>  
 <span data-ttu-id="2c21b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c21b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c21b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c21b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c21b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c21b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c21b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c21b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
