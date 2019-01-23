---
title: ICorDebugValue::GetAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b88c49ba93ff3c4cc3f5c7a656dfa5da6e82109e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559840"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="015da-102">ICorDebugValue::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="015da-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="015da-103">Ruft die Adresse des Objekts "ICorDebugValue", der gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="015da-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="015da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="015da-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="015da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="015da-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="015da-106">[out] Zeiger auf eine `CORDB_ADDRESS` Objekt, das die Adresse des Wertobjekts angibt.</span><span class="sxs-lookup"><span data-stu-id="015da-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="015da-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="015da-107">Remarks</span></span>  
 <span data-ttu-id="015da-108">Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="015da-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="015da-109">Dies kann passieren, wenn der Wert, zumindest teilweise in Registern ist oder in einem Garbage Collector-Handle (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="015da-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="015da-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="015da-110">Requirements</span></span>  
 <span data-ttu-id="015da-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="015da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="015da-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="015da-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="015da-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="015da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="015da-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="015da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="015da-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="015da-115">See also</span></span>

