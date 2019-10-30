---
title: CorpubPublish-Co-Klasse
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: 89af99fab1f1265701e0dbfe74a46000cb3bfaa6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132150"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="90205-102">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="90205-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="90205-103">Stellt Schnittstellen für die Veröffentlichung von Informationen über Anwendungsdomänen und Prozesse bereit.</span><span class="sxs-lookup"><span data-stu-id="90205-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90205-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90205-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="90205-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="90205-105">Interfaces</span></span>  
  
|<span data-ttu-id="90205-106">Interface</span><span class="sxs-lookup"><span data-stu-id="90205-106">Interface</span></span>|<span data-ttu-id="90205-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90205-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="90205-108">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90205-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="90205-109">Stellt Methoden zum Veröffentlichen von Informationen zu Prozessen und Anwendungs Domänen in diesen Prozessen bereit.</span><span class="sxs-lookup"><span data-stu-id="90205-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="90205-110">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90205-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="90205-111">Stellt eine Anwendungsdomäne in einem Prozess dar und stellt Informationen zu einer Anwendungsdomäne bereit.</span><span class="sxs-lookup"><span data-stu-id="90205-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="90205-112">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90205-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="90205-113">Stellt Methoden bereit, die eine Auflistung von Anwendungs Domänen durchlaufen, die derzeit in einem Prozess vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="90205-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="90205-114">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90205-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="90205-115">Stellt einen Prozess dar, der auf einem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90205-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="90205-116">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90205-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="90205-117">Stellt Methoden bereit, die eine Auflistung von Prozessen durchlaufen, die auf einem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="90205-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90205-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90205-118">Remarks</span></span>  
 <span data-ttu-id="90205-119">Ein typisches Veröffentlichungs Szenario umfasst einen Entwickler, der verwalteten Code Debuggen möchte, der auf einem Computer innerhalb einer Anwendungsdomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90205-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="90205-120">In der Hostingumgebung wird möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="90205-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="90205-121">Der Entwickler möchte eine grafische Benutzeroberfläche oder andere Mittel verwenden, um alle Prozesse aufzulisten, die auf dem Computer ausgeführt werden, und einen bestimmten Prozess auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="90205-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="90205-122">Die Auflistung sollte alle Anwendungs Domänen innerhalb von Prozessen enthalten, die verwalteten Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="90205-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="90205-123">Der Entwickler kann dann die jeweilige Anwendungsdomäne identifizieren und dieser Domäne einen Debugger anfügen.</span><span class="sxs-lookup"><span data-stu-id="90205-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90205-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90205-124">Requirements</span></span>  
 <span data-ttu-id="90205-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90205-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90205-126">**Header:** Corpub. idl</span><span class="sxs-lookup"><span data-stu-id="90205-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="90205-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90205-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90205-128">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90205-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90205-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90205-129">See also</span></span>

- [<span data-ttu-id="90205-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="90205-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
