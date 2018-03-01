---
title: _EFN_GetManagedObjectName-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c29aa82143c34a229cee0a5b000657c9add22bd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="b562f-102">_EFN_GetManagedObjectName-Funktion</span><span class="sxs-lookup"><span data-stu-id="b562f-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="b562f-103">Ruft den Namen des Typs mithilfe der bereitgestellten verwalteten Objektzeiger ab.</span><span class="sxs-lookup"><span data-stu-id="b562f-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b562f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b562f-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b562f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b562f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="b562f-106">[in] Ein Zeiger auf den Client Debuggen.</span><span class="sxs-lookup"><span data-stu-id="b562f-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="b562f-107">[in] Ein Zeiger des verwalteten Objekts.</span><span class="sxs-lookup"><span data-stu-id="b562f-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="b562f-108">szName</span><span class="sxs-lookup"><span data-stu-id="b562f-108">szName</span></span>  
 <span data-ttu-id="b562f-109">[out] Der Name des Typs.</span><span class="sxs-lookup"><span data-stu-id="b562f-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="b562f-110">[out] Die Anzahl der Zeichen im Zeichenfolgenpuffer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b562f-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b562f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b562f-111">Remarks</span></span>  
 <span data-ttu-id="b562f-112">Es ist kein verwalteter Code auf dem Thread derzeit im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und dem Fehlercode 0 x 1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="b562f-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b562f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b562f-113">Requirements</span></span>  
 <span data-ttu-id="b562f-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b562f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b562f-115">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="b562f-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="b562f-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b562f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b562f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b562f-117">See Also</span></span>  
 [<span data-ttu-id="b562f-118">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="b562f-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
