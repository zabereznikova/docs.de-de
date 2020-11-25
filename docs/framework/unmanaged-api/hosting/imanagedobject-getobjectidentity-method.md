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
ms.openlocfilehash: fc74b84bccceb1772bf3642e51ec88c562ce5dce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730712"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="e9273-102">IManagedObject::GetObjectIdentity-Methode</span><span class="sxs-lookup"><span data-stu-id="e9273-102">IManagedObject::GetObjectIdentity Method</span></span>

<span data-ttu-id="e9273-103">Ruft die Identität dieses verwalteten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="e9273-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9273-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9273-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9273-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9273-105">Parameters</span></span>  

 `pBSTRGUID`  
 <span data-ttu-id="e9273-106">vorgenommen Ein Zeiger auf die GUID des Prozesses, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="e9273-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="e9273-107">vorgenommen Ein Zeiger auf die ID der Anwendungsdomäne des Objekts.</span><span class="sxs-lookup"><span data-stu-id="e9273-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="e9273-108">vorgenommen Ein Zeiger auf den Index des Objekts in der klassischen com-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e9273-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9273-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9273-109">Remarks</span></span>  

 <span data-ttu-id="e9273-110">Die Identität eines verwalteten Objekts umfasst die Prozess-GUID, die Anwendungs Domänen-ID und den Index des Objekts in der klassischen com-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e9273-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9273-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9273-111">Requirements</span></span>  

 <span data-ttu-id="e9273-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9273-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9273-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e9273-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9273-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e9273-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9273-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9273-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9273-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9273-116">See also</span></span>

- [<span data-ttu-id="e9273-117">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9273-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
