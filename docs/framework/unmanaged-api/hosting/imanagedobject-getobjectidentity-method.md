---
title: IManagedObject::GetObjectIdentity-Methode
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291246169a5cc2c95b117bc55bc269791885b2ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749094"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="6ea7a-102">IManagedObject::GetObjectIdentity-Methode</span><span class="sxs-lookup"><span data-stu-id="6ea7a-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="6ea7a-103">Ruft die Identität dieser verwalteten Objekts.</span><span class="sxs-lookup"><span data-stu-id="6ea7a-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea7a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ea7a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea7a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ea7a-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="6ea7a-106">[out] Ein Zeiger auf die GUID des Prozesses, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="6ea7a-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="6ea7a-107">[out] Ein Zeiger auf die ID der Anwendungsdomäne des Objekts.</span><span class="sxs-lookup"><span data-stu-id="6ea7a-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="6ea7a-108">[out] Ein Zeiger auf den Index des Objekts, in der klassischen COM-V-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6ea7a-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ea7a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ea7a-109">Remarks</span></span>  
 <span data-ttu-id="6ea7a-110">In der klassischen COM-V-Tabelle enthält die Identität eines verwalteten Objekts GUID-Prozessen, Anwendungsdomänen-ID und der Index des Objekts.</span><span class="sxs-lookup"><span data-stu-id="6ea7a-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea7a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ea7a-111">Requirements</span></span>  
 <span data-ttu-id="6ea7a-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea7a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea7a-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ea7a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ea7a-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6ea7a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ea7a-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea7a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea7a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ea7a-116">See also</span></span>

- [<span data-ttu-id="6ea7a-117">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ea7a-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
