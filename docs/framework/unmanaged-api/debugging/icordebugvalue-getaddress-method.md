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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986855"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="cde1f-102">ICorDebugValue::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="cde1f-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="cde1f-103">Ruft die Adresse des Objekts "ICorDebugValue", der gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="cde1f-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cde1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cde1f-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cde1f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cde1f-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="cde1f-106">[out] Zeiger auf eine `CORDB_ADDRESS` Objekt, das die Adresse des Wertobjekts angibt.</span><span class="sxs-lookup"><span data-stu-id="cde1f-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cde1f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cde1f-107">Remarks</span></span>  
 <span data-ttu-id="cde1f-108">Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cde1f-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="cde1f-109">Dies kann passieren, wenn der Wert, zumindest teilweise in Registern ist oder in einem Garbage Collector-Handle (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="cde1f-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cde1f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cde1f-110">Requirements</span></span>  
 <span data-ttu-id="cde1f-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cde1f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cde1f-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cde1f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cde1f-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cde1f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cde1f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cde1f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde1f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cde1f-115">See also</span></span>
