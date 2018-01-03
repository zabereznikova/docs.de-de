---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f920ceb802231112ef1b855fd0a78d3a0e6ca4c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="23850-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="23850-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="23850-103">Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="23850-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="23850-104">Ein *Bucket* ist eine Auflistung von Fehlerdaten, die auf den gleichen Codefehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="23850-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="23850-105">*Watson* bezieht sich auf eine Reihe von Technologien zum Sammeln und Analysieren von Daten, die eine Ausnahme zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="23850-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23850-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="23850-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23850-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="23850-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="23850-108">[out] Ein Zeiger auf eine [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) Struktur, die Fehlerdaten für die Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="23850-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23850-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23850-109">Requirements</span></span>  
 <span data-ttu-id="23850-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23850-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23850-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23850-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23850-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23850-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23850-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23850-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23850-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23850-114">See Also</span></span>  
 [<span data-ttu-id="23850-115">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23850-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
