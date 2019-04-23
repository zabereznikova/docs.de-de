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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05d9eef36885aee05d88f7da994c8b168c3221b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130532"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="719e5-102">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="719e5-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="719e5-103">Stellt Schnittstellen für die Veröffentlichung von Informationen über Anwendungsdomänen und Prozesse bereit.</span><span class="sxs-lookup"><span data-stu-id="719e5-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="719e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="719e5-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="719e5-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="719e5-105">Interfaces</span></span>  
  
|<span data-ttu-id="719e5-106">Interface</span><span class="sxs-lookup"><span data-stu-id="719e5-106">Interface</span></span>|<span data-ttu-id="719e5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="719e5-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="719e5-108">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="719e5-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="719e5-109">Stellt Methoden für die Veröffentlichung von Informationen zu Prozessen und Anwendungsdomänen in diesen Prozessen bereit.</span><span class="sxs-lookup"><span data-stu-id="719e5-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="719e5-110">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="719e5-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="719e5-111">Stellt dar, und enthält Informationen zu einer Anwendungsdomäne in einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="719e5-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="719e5-112">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="719e5-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="719e5-113">Bietet Methoden, die eine Auflistung von Anwendungsdomänen durchlaufen, die zurzeit innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="719e5-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="719e5-114">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="719e5-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="719e5-115">Stellt einen Prozess, der auf einem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="719e5-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="719e5-116">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="719e5-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="719e5-117">Bietet Methoden, die eine Auflistung der Prozesse durchlaufen, die auf einem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="719e5-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="719e5-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="719e5-118">Remarks</span></span>  
 <span data-ttu-id="719e5-119">Ein typisches Szenario für die Veröffentlichung umfasst einen Entwickler möchte, verwalteten Code Debuggen, die auf einem Computer innerhalb einer Anwendungsdomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="719e5-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="719e5-120">Die hostumgebung möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="719e5-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="719e5-121">Der Entwickler möchte eine grafische Benutzeroberfläche oder eine andere Möglichkeit zum Auflisten aller Prozesse, die auf dem Computer ausgeführt werden, und wählen Sie einen bestimmten Prozess.</span><span class="sxs-lookup"><span data-stu-id="719e5-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="719e5-122">Die Liste sollte alle Anwendungsdomänen innerhalb von Prozessen enthalten, die verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="719e5-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="719e5-123">Der Entwickler kann dann identifizieren die spezifischen Anwendungsdomäne und Anfügen eines Debuggers an der Domäne.</span><span class="sxs-lookup"><span data-stu-id="719e5-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="719e5-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="719e5-124">Requirements</span></span>  
 <span data-ttu-id="719e5-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="719e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="719e5-126">**Header:** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="719e5-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="719e5-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="719e5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="719e5-128">**.NET Framework-Versionen:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="719e5-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="719e5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="719e5-129">See also</span></span>

- [<span data-ttu-id="719e5-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="719e5-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
