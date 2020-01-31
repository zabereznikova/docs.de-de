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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790541"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="b04da-102">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b04da-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="b04da-103">Stellt Methoden bereit, die auf Informationen zugreifen, die zu einem Prozess angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b04da-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b04da-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b04da-104">Methods</span></span>  
  
|<span data-ttu-id="b04da-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="b04da-105">Method</span></span>|<span data-ttu-id="b04da-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b04da-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b04da-107">EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="b04da-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="b04da-108">Ruft eine [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) -Instanz ab, die die Anwendungs Domänen in dem Prozess enthält, auf den von diesem `ICorPublishProcess`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b04da-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="b04da-109">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="b04da-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="b04da-110">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von diesem `ICorPublishProcess`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b04da-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="b04da-111">GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="b04da-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="b04da-112">Ruft den Betriebssystem Bezeichner für den Prozess ab, auf den von diesem `ICorPublishProcess`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b04da-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="b04da-113">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="b04da-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="b04da-114">Ruft einen Wert ab, der angibt, ob der Prozess, auf den dieser `ICorPublishProcess` verweist, bekanntermaßen verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b04da-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b04da-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b04da-115">Requirements</span></span>  
 <span data-ttu-id="b04da-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b04da-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04da-117">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="b04da-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b04da-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b04da-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b04da-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04da-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04da-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b04da-120">See also</span></span>

- [<span data-ttu-id="b04da-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b04da-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b04da-122">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="b04da-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
