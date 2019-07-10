---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 276a69deecccc91b3c511403c2bd0d5c0baabd9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772800"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="5f488-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="5f488-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="5f488-103">Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="5f488-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="5f488-104">Ein *Bucket* ist eine Sammlung von Daten von Fehlern, die mit den gleichen Codefehler verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="5f488-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="5f488-105">*Dr. Watson* bezieht sich auf eine Reihe von Technologien zum Sammeln und Analysieren von Daten, die eine Ausnahme zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5f488-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f488-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f488-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f488-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f488-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="5f488-108">[out] Ein Zeiger auf eine [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) Struktur, die Fehlerdaten, die für die ausgelöste Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="5f488-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f488-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f488-109">Requirements</span></span>  
 <span data-ttu-id="5f488-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f488-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f488-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f488-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f488-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5f488-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f488-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f488-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f488-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f488-114">See also</span></span>

- [<span data-ttu-id="5f488-115">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f488-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
