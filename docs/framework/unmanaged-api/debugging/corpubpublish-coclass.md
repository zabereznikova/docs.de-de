---
title: CorpubPublish-Co-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="b4f81-102">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="b4f81-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="b4f81-103">Stellt Schnittstellen für die Veröffentlichung von Informationen über Anwendungsdomänen und Prozesse bereit.</span><span class="sxs-lookup"><span data-stu-id="b4f81-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4f81-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b4f81-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4f81-105">Interfaces</span></span>  
  
|<span data-ttu-id="b4f81-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4f81-106">Interface</span></span>|<span data-ttu-id="b4f81-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4f81-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b4f81-108">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4f81-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="b4f81-109">Stellt Methoden für die Veröffentlichung von Informationen über Prozesse und die Anwendungsdomänen in diesen Prozessen bereit.</span><span class="sxs-lookup"><span data-stu-id="b4f81-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="b4f81-110">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4f81-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="b4f81-111">Stellt dar, und enthält Informationen zu einer Anwendungsdomäne in einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="b4f81-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="b4f81-112">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4f81-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="b4f81-113">Enthält Methoden, die eine Auflistung von Anwendungsdomänen durchlaufen, die derzeit innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b4f81-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="b4f81-114">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4f81-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="b4f81-115">Entspricht einem Prozess, der auf einem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4f81-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="b4f81-116">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4f81-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="b4f81-117">Enthält Methoden, die eine Auflistung von Prozessen durchlaufen, die auf einem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4f81-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f81-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4f81-118">Remarks</span></span>  
 <span data-ttu-id="b4f81-119">Ein typisches Szenario für die publishing umfasst einen Entwickler möchte, Debuggen Sie verwalteten Code, der auf einem Computer in einer Anwendungsdomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4f81-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="b4f81-120">Die hostumgebung möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4f81-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="b4f81-121">Der Entwickler möchte eine grafische Benutzeroberfläche oder andere Weise verwenden, um alle Prozesse aufzulisten, die auf dem Computer ausgeführt werden, und wählen Sie einen bestimmten Prozess.</span><span class="sxs-lookup"><span data-stu-id="b4f81-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="b4f81-122">Die Auflistung sollte alle Anwendungsdomänen innerhalb von Prozessen enthalten, die verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4f81-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="b4f81-123">Klicken Sie dann kann den bestimmten Anwendungsdomäne zu identifizieren und Anfügen eines Debuggers an, dass diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="b4f81-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f81-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4f81-124">Requirements</span></span>  
 <span data-ttu-id="b4f81-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f81-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f81-126">**Header:** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="b4f81-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="b4f81-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f81-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4f81-128">**.NET Framework-Versionen:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f81-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f81-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4f81-129">See Also</span></span>  
 [<span data-ttu-id="b4f81-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b4f81-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
