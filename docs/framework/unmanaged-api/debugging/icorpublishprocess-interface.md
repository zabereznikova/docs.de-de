---
title: ICorPublishProcess-Schnittstelle
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
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 765be4e0ae7657d169ea561bc6a36bcf8cc11153
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="6878d-102">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6878d-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="6878d-103">Stellt Methoden, die Zugriff auf Informationen, die angezeigt werden, zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="6878d-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6878d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6878d-104">Methods</span></span>  
  
|<span data-ttu-id="6878d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6878d-105">Method</span></span>|<span data-ttu-id="6878d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6878d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6878d-107">EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="6878d-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="6878d-108">Ruft eine [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Anwendungsdomänen im Prozess verwiesen, die von diesem enthält `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="6878d-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="6878d-109">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="6878d-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="6878d-110">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, auf die verwiesen wird von diesem `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="6878d-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="6878d-111">GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="6878d-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="6878d-112">Ruft den Bezeichner des Betriebssystems für den Prozess, auf die verwiesen wird von diesem `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="6878d-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="6878d-113">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="6878d-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="6878d-114">Ruft einen Wert, der angibt, ob dies der Prozess verweist `ICorPublishProcess` ist bekanntermaßen mit verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6878d-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6878d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6878d-115">Requirements</span></span>  
 <span data-ttu-id="6878d-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6878d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6878d-117">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6878d-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6878d-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6878d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6878d-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6878d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6878d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6878d-120">See Also</span></span>  
 [<span data-ttu-id="6878d-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6878d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6878d-122">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="6878d-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
