---
title: ICorPublishProcess::EnumAppDomains-Methode
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
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 938c022788d5ed9f0e28f794432017748dc096e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="1a435-102">ICorPublishProcess::EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="1a435-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="1a435-103">Ruft einen Enumerator für die Anwendungsdomänen im Prozess, der von diesem verwiesen wird [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1a435-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a435-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a435-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a435-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a435-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1a435-106">[out] Ein Zeiger auf die Adresse des ein [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Iteration durch die Auflistung der Anwendungsdomänen in diesem Prozess ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1a435-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a435-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a435-107">Remarks</span></span>  
 <span data-ttu-id="1a435-108">Die Liste der Anwendungsdomänen basiert auf einer Momentaufnahme der Anwendungsdomänen, die vorhanden sind bei der `EnumAppDomains` -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1a435-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="1a435-109">Diese Methode kann mehrmals aufgerufen werden, zum Erstellen einer neuen auf dem neuesten Stand Liste.</span><span class="sxs-lookup"><span data-stu-id="1a435-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="1a435-110">Vorhandene Listen, werden nachfolgende Aufrufe dieser Methode nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="1a435-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="1a435-111">Wenn der Prozess beendet wurde, `EnumAppDomains` mit HRESULT-Wert CORDBG_E_PROCESS_TERMINATED fehl.</span><span class="sxs-lookup"><span data-stu-id="1a435-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a435-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a435-112">Requirements</span></span>  
 <span data-ttu-id="1a435-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a435-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a435-114">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1a435-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1a435-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a435-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a435-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a435-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a435-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a435-117">See Also</span></span>  
 [<span data-ttu-id="1a435-118">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a435-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
