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
ms.openlocfilehash: 8ee59e9d416d1c53312e4fccb6953f20b03b29b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693085"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="9eae8-102">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9eae8-102">ICorPublishProcess Interface</span></span>

<span data-ttu-id="9eae8-103">Stellt Methoden bereit, die auf Informationen zugreifen, die zu einem Prozess angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9eae8-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9eae8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9eae8-104">Methods</span></span>  
  
|<span data-ttu-id="9eae8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9eae8-105">Method</span></span>|<span data-ttu-id="9eae8-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9eae8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9eae8-107">EnumAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="9eae8-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="9eae8-108">Ruft eine [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) -Instanz ab, die die Anwendungs Domänen in dem Prozess enthält, auf den von verwiesen wird `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="9eae8-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="9eae8-109">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="9eae8-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="9eae8-110">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von verwiesen wird `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="9eae8-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="9eae8-111">GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="9eae8-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="9eae8-112">Ruft den Betriebssystem Bezeichner für den Prozess ab, auf den von verwiesen wird `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="9eae8-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="9eae8-113">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="9eae8-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="9eae8-114">Ruft einen Wert ab, der angibt, ob der Prozess, auf den von verwiesen wird `ICorPublishProcess` , bekanntermaßen verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9eae8-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9eae8-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9eae8-115">Requirements</span></span>  

 <span data-ttu-id="9eae8-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eae8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eae8-117">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="9eae8-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9eae8-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9eae8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9eae8-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eae8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eae8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9eae8-120">See also</span></span>

- [<span data-ttu-id="9eae8-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9eae8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9eae8-122">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="9eae8-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
