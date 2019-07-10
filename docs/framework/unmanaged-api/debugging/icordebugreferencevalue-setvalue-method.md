---
title: ICorDebugReferenceValue::SetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804aa4a6508713b2d6f2d154fc47e09638994468
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747367"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="6def7-102">ICorDebugReferenceValue::SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6def7-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="6def7-103">Legt fest, die angegebenen Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="6def7-103">Sets the specified memory address.</span></span> <span data-ttu-id="6def7-104">D.h., legt diese Methode ICorDebugReferenceValue, um auf ein Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6def7-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6def7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6def7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6def7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6def7-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="6def7-107">[in] Ein `CORDB_ADDRESS` Wert, der angibt, die Adresse des Objekts, dem diese `ICorDebugReferenceValue` Punkte.</span><span class="sxs-lookup"><span data-stu-id="6def7-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6def7-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6def7-108">Requirements</span></span>  
 <span data-ttu-id="6def7-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6def7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6def7-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6def7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6def7-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6def7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6def7-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6def7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
