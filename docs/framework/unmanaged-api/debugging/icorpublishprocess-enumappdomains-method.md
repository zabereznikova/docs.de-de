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
ms.openlocfilehash: aa76bf511ff1e1710a7ff86ad2ac97665969f2bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140439"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="44aea-102">ICorPublishProcess::EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="44aea-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="44aea-103">Ruft einen Enumerator für die Anwendungs Domänen in dem Prozess ab, auf den von diesem [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="44aea-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44aea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44aea-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44aea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44aea-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="44aea-106">vorgenommen Ein Zeiger auf die Adresse einer [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Iterationen durch die Auflistung von Anwendungs Domänen in diesem Prozess ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="44aea-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44aea-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44aea-107">Remarks</span></span>  
 <span data-ttu-id="44aea-108">Die Liste der Anwendungs Domänen basiert auf einer Momentaufnahme der Anwendungs Domänen, die vorhanden sind, wenn die `EnumAppDomains`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="44aea-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="44aea-109">Diese Methode kann mehrmals aufgerufen werden, um eine neue aktuelle Liste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="44aea-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="44aea-110">Bei nachfolgenden Aufrufen dieser Methode werden vorhandene Listen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="44aea-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="44aea-111">Wenn der Prozess beendet wurde, wird `EnumAppDomains` mit einem HRESULT-Wert von CORDBG_E_PROCESS_TERMINATED fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="44aea-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44aea-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44aea-112">Requirements</span></span>  
 <span data-ttu-id="44aea-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44aea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44aea-114">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="44aea-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="44aea-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44aea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44aea-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44aea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44aea-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44aea-117">See also</span></span>

- [<span data-ttu-id="44aea-118">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44aea-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
