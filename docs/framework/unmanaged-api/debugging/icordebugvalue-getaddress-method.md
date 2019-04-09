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
ms.openlocfilehash: ac550ee7b1d66612557b30d15c275c90cf09b8af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187333"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="4da48-102">ICorDebugValue::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="4da48-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="4da48-103">Ruft die Adresse des Objekts "ICorDebugValue", der gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="4da48-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4da48-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4da48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4da48-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="4da48-106">[out] Zeiger auf eine `CORDB_ADDRESS` Objekt, das die Adresse des Wertobjekts angibt.</span><span class="sxs-lookup"><span data-stu-id="4da48-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da48-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4da48-107">Remarks</span></span>  
 <span data-ttu-id="4da48-108">Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4da48-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="4da48-109">Dies kann passieren, wenn der Wert, zumindest teilweise in Registern ist oder in einem Garbage Collector-Handle (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="4da48-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4da48-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4da48-110">Requirements</span></span>  
 <span data-ttu-id="4da48-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da48-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da48-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4da48-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4da48-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da48-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4da48-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4da48-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4da48-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4da48-115">See also</span></span>
