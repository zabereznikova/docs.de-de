---
title: IManagedObject::GetObjectIdentity-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetObjectIdentity
api_location: mscoree.dll
api_type: COM
f1_keywords: GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5654865c557e6e004685f66753366d7cb575919
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="25a30-102">IManagedObject::GetObjectIdentity-Methode</span><span class="sxs-lookup"><span data-stu-id="25a30-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="25a30-103">Ruft die Identität dieses verwalteten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="25a30-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25a30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25a30-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25a30-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25a30-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="25a30-106">[out] Ein Zeiger auf die GUID des Prozesses, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="25a30-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="25a30-107">[out] Ein Zeiger auf die ID der Anwendungsdomäne des Objekts.</span><span class="sxs-lookup"><span data-stu-id="25a30-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="25a30-108">[out] Ein Zeiger auf den Index des Objekts, in der klassischen COM-V-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="25a30-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25a30-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25a30-109">Remarks</span></span>  
 <span data-ttu-id="25a30-110">Die Identität eines verwalteten Objekts enthält die Prozess-GUID, Anwendungsdomänen-ID und der Index des Objekts in der klassischen COM-V-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="25a30-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25a30-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25a30-111">Requirements</span></span>  
 <span data-ttu-id="25a30-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25a30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25a30-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25a30-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25a30-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="25a30-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25a30-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25a30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a30-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25a30-116">See Also</span></span>  
 [<span data-ttu-id="25a30-117">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25a30-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
