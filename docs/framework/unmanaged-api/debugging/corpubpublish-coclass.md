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
ms.openlocfilehash: c73eab14bf6f9f9599bed79f4c5f85ed035c0518
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722348"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="8eec6-102">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="8eec6-102">CorpubPublish Coclass</span></span>

<span data-ttu-id="8eec6-103">Stellt Schnittstellen für die Veröffentlichung von Informationen über Anwendungsdomänen und Prozesse bereit.</span><span class="sxs-lookup"><span data-stu-id="8eec6-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eec6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8eec6-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="8eec6-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8eec6-105">Interfaces</span></span>  
  
|<span data-ttu-id="8eec6-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eec6-106">Interface</span></span>|<span data-ttu-id="8eec6-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8eec6-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="8eec6-108">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eec6-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="8eec6-109">Stellt Methoden zum Veröffentlichen von Informationen zu Prozessen und Anwendungs Domänen in diesen Prozessen bereit.</span><span class="sxs-lookup"><span data-stu-id="8eec6-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="8eec6-110">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eec6-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="8eec6-111">Stellt eine Anwendungsdomäne in einem Prozess dar und stellt Informationen zu einer Anwendungsdomäne bereit.</span><span class="sxs-lookup"><span data-stu-id="8eec6-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="8eec6-112">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eec6-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="8eec6-113">Stellt Methoden bereit, die eine Auflistung von Anwendungs Domänen durchlaufen, die derzeit in einem Prozess vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8eec6-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="8eec6-114">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eec6-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="8eec6-115">Stellt einen Prozess dar, der auf einem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8eec6-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="8eec6-116">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8eec6-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="8eec6-117">Stellt Methoden bereit, die eine Auflistung von Prozessen durchlaufen, die auf einem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8eec6-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eec6-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8eec6-118">Remarks</span></span>  

 <span data-ttu-id="8eec6-119">Ein typisches Veröffentlichungs Szenario umfasst einen Entwickler, der verwalteten Code Debuggen möchte, der auf einem Computer innerhalb einer Anwendungsdomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8eec6-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="8eec6-120">In der Hostingumgebung wird möglicherweise mehr als eine Anwendungsdomäne innerhalb eines Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8eec6-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="8eec6-121">Der Entwickler möchte eine grafische Benutzeroberfläche oder andere Mittel verwenden, um alle Prozesse aufzulisten, die auf dem Computer ausgeführt werden, und einen bestimmten Prozess auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8eec6-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="8eec6-122">Die Auflistung sollte alle Anwendungs Domänen innerhalb von Prozessen enthalten, die verwalteten Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="8eec6-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="8eec6-123">Der Entwickler kann dann die jeweilige Anwendungsdomäne identifizieren und dieser Domäne einen Debugger anfügen.</span><span class="sxs-lookup"><span data-stu-id="8eec6-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eec6-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8eec6-124">Requirements</span></span>  

 <span data-ttu-id="8eec6-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eec6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eec6-126">**Header:** Corpub. idl</span><span class="sxs-lookup"><span data-stu-id="8eec6-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="8eec6-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8eec6-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8eec6-128">**.NET Framework Versionen:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eec6-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eec6-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8eec6-129">See also</span></span>

- [<span data-ttu-id="8eec6-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8eec6-130">Debugging</span></span>](index.md)
