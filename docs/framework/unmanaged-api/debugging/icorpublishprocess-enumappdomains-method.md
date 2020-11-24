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
ms.openlocfilehash: 2acf8fb507ab617e066a31c9c2657b1ef0d18e47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693280"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="00612-102">ICorPublishProcess::EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="00612-102">ICorPublishProcess::EnumAppDomains Method</span></span>

<span data-ttu-id="00612-103">Ruft einen Enumerator für die Anwendungs Domänen in dem Prozess ab, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md)verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00612-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00612-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00612-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00612-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00612-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="00612-106">vorgenommen Ein Zeiger auf die Adresse einer [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) -Instanz, die Iterationen durch die Auflistung von Anwendungs Domänen in diesem Prozess ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="00612-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00612-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00612-107">Remarks</span></span>  

 <span data-ttu-id="00612-108">Die Liste der Anwendungs Domänen basiert auf einer Momentaufnahme der Anwendungs Domänen, die beim Aufrufen der- `EnumAppDomains` Methode vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="00612-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="00612-109">Diese Methode kann mehrmals aufgerufen werden, um eine neue aktuelle Liste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00612-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="00612-110">Bei nachfolgenden Aufrufen dieser Methode werden vorhandene Listen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="00612-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="00612-111">Wenn der Prozess beendet wurde, `EnumAppDomains` schlägt mit dem HRESULT-Wert CORDBG_E_PROCESS_TERMINATED fehl.</span><span class="sxs-lookup"><span data-stu-id="00612-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00612-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="00612-112">Requirements</span></span>  

 <span data-ttu-id="00612-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00612-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00612-114">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="00612-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="00612-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00612-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00612-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00612-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00612-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00612-117">See also</span></span>

- [<span data-ttu-id="00612-118">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00612-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
