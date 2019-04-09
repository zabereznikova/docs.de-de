---
title: ICorPublishProcess::EnumAppDomains-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 173a7d6793bec9262efb661d56e3a371d0bf9b47
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164605"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="dfff9-102">ICorPublishProcess::EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="dfff9-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="dfff9-103">Ruft einen Enumerator für die Anwendungsdomänen im Prozess, der von diesem verwiesen wird [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dfff9-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfff9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfff9-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfff9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfff9-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="dfff9-106">[out] Ein Zeiger auf die Adresse einer [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Iteration durch die Auflistung von Anwendungsdomänen in diesem Prozess ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="dfff9-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfff9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfff9-107">Remarks</span></span>  
 <span data-ttu-id="dfff9-108">Die Liste der Anwendungsdomänen basiert darauf, dass eine Momentaufnahme der Anwendungsdomänen, die vorhanden sind bei der `EnumAppDomains` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dfff9-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="dfff9-109">Diese Methode kann mehr als einmal aufgerufen werden, um eine neue auf dem neuesten Stand Liste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dfff9-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="dfff9-110">Vorhandene Listen werden durch nachfolgende Aufrufe dieser Methode nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="dfff9-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="dfff9-111">Wenn der Prozess beendet wurde, `EnumAppDomains` mit HRESULT-Wert CORDBG_E_PROCESS_TERMINATED fehl.</span><span class="sxs-lookup"><span data-stu-id="dfff9-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfff9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfff9-112">Requirements</span></span>  
 <span data-ttu-id="dfff9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfff9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfff9-114">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="dfff9-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="dfff9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfff9-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dfff9-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="dfff9-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfff9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfff9-117">See also</span></span>

- [<span data-ttu-id="dfff9-118">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfff9-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
