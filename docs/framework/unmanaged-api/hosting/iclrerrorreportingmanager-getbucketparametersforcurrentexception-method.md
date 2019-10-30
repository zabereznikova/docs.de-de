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
ms.openlocfilehash: b24f8ed4f5e2c6e0022f5599f2ab8c44a30a561a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129275"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="1ef84-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="1ef84-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="1ef84-103">Ruft den Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="1ef84-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="1ef84-104">Ein *Bucket* ist eine Auflistung von Fehler Daten, die sich auf denselben Code Fehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="1ef84-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="1ef84-105">*Watson* verweist auf eine Reihe von Technologien zum Erfassen und Analysieren von Daten, die einer Ausnahme zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1ef84-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef84-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ef84-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ef84-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ef84-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="1ef84-108">vorgenommen Ein Zeiger auf eine [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) -Struktur, die Fehler Daten für die Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="1ef84-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef84-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ef84-109">Requirements</span></span>  
 <span data-ttu-id="1ef84-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ef84-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef84-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1ef84-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ef84-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ef84-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ef84-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef84-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ef84-114">See also</span></span>

- [<span data-ttu-id="1ef84-115">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ef84-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
