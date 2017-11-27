---
title: ICorPublishProcess-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cb62da277ff13bea33969bb9c728cac5d5a15554
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="3f48a-102">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f48a-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="3f48a-103">Stellt Methoden, die Zugriff auf Informationen, die angezeigt werden, zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="3f48a-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f48a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3f48a-104">Methods</span></span>  
  
|<span data-ttu-id="3f48a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3f48a-105">Method</span></span>|<span data-ttu-id="3f48a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f48a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f48a-107">EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="3f48a-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="3f48a-108">Ruft eine [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Anwendungsdomänen im Prozess verwiesen, die von diesem enthält `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="3f48a-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="3f48a-109">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="3f48a-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="3f48a-110">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, auf die verwiesen wird von diesem `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="3f48a-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="3f48a-111">GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="3f48a-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="3f48a-112">Ruft den Bezeichner des Betriebssystems für den Prozess, auf die verwiesen wird von diesem `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="3f48a-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="3f48a-113">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="3f48a-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="3f48a-114">Ruft einen Wert, der angibt, ob dies der Prozess verweist `ICorPublishProcess` ist bekanntermaßen mit verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3f48a-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f48a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f48a-115">Requirements</span></span>  
 <span data-ttu-id="3f48a-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f48a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f48a-117">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3f48a-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3f48a-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f48a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f48a-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f48a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f48a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f48a-120">See Also</span></span>  
 [<span data-ttu-id="3f48a-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3f48a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3f48a-122">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="3f48a-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
