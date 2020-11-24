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
ms.openlocfilehash: 33927cc0e3a3cdaad70d437f9dd5ca5dfdcdc46b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673557"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="71769-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="71769-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>

<span data-ttu-id="71769-103">Ruft den Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="71769-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="71769-104">Ein *Bucket* ist eine Auflistung von Fehler Daten, die sich auf denselben Code Fehler beziehen.</span><span class="sxs-lookup"><span data-stu-id="71769-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="71769-105">*Watson* verweist auf eine Reihe von Technologien zum Erfassen und Analysieren von Daten, die einer Ausnahme zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="71769-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71769-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="71769-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71769-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="71769-107">Parameters</span></span>  

 `pParams`  
 <span data-ttu-id="71769-108">vorgenommen Ein Zeiger auf eine [BucketParameters](bucketparameters-structure.md) -Struktur, die Fehler Daten für die Ausnahme enthält.</span><span class="sxs-lookup"><span data-stu-id="71769-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71769-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71769-109">Requirements</span></span>  

 <span data-ttu-id="71769-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71769-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71769-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="71769-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71769-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71769-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71769-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71769-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71769-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71769-114">See also</span></span>

- [<span data-ttu-id="71769-115">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71769-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
