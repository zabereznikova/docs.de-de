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
ms.openlocfilehash: 1b40ed8e107d30c22b4ade25d29376b1b74583d1
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842412"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="43db8-102">IManagedObject::GetObjectIdentity-Methode</span><span class="sxs-lookup"><span data-stu-id="43db8-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="43db8-103">Ruft die Identität dieses verwalteten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="43db8-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43db8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43db8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43db8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43db8-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="43db8-106">vorgenommen Ein Zeiger auf die GUID des Prozesses, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="43db8-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="43db8-107">vorgenommen Ein Zeiger auf die ID der Anwendungsdomäne des Objekts.</span><span class="sxs-lookup"><span data-stu-id="43db8-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="43db8-108">vorgenommen Ein Zeiger auf den Index des Objekts in der klassischen com-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43db8-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43db8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43db8-109">Remarks</span></span>  
 <span data-ttu-id="43db8-110">Die Identität eines verwalteten Objekts umfasst die Prozess-GUID, die Anwendungs Domänen-ID und den Index des Objekts in der klassischen com-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43db8-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43db8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43db8-111">Requirements</span></span>  
 <span data-ttu-id="43db8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43db8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43db8-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="43db8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43db8-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="43db8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43db8-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43db8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43db8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43db8-116">See also</span></span>

- [<span data-ttu-id="43db8-117">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43db8-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
