---
title: ICorPublishProcess-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182961"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="bc3fb-102">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc3fb-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="bc3fb-103">Bietet Methoden, die Informationen, die angezeigt wird, werden zu einem Prozess zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bc3fb-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc3fb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc3fb-104">Methods</span></span>  
  
|<span data-ttu-id="bc3fb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bc3fb-105">Method</span></span>|<span data-ttu-id="bc3fb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc3fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc3fb-107">EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3fb-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="bc3fb-108">Ruft eine [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Anwendungsdomänen im Prozess auf die dieses enthält `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="bc3fb-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="bc3fb-109">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3fb-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="bc3fb-110">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, der auf die dieses `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="bc3fb-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="bc3fb-111">GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3fb-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="bc3fb-112">Ruft den Bezeichner für den Prozess, der auf die dieses `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="bc3fb-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="bc3fb-113">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3fb-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="bc3fb-114">Ruft einen Wert, der angibt, ob von dieser vom Prozess verwiesen `ICorPublishProcess` ist bekannt, dass verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bc3fb-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc3fb-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc3fb-115">Requirements</span></span>  
 <span data-ttu-id="bc3fb-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc3fb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc3fb-117">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="bc3fb-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bc3fb-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc3fb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc3fb-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc3fb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3fb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc3fb-120">See also</span></span>

- [<span data-ttu-id="bc3fb-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc3fb-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bc3fb-122">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="bc3fb-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
