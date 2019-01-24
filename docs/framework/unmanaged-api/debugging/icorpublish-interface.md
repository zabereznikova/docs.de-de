---
title: ICorPublish-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1dea8cc54c68db333c409e3bd7b3e4211bd52ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713966"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="09715-102">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09715-102">ICorPublish Interface</span></span>
<span data-ttu-id="09715-103">Fungiert als allgemeine Schnittstelle für die Veröffentlichung von Informationen zu Prozessen und Informationen zu den Anwendungsdomänen in diesen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="09715-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09715-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="09715-104">Methods</span></span>  
  
|<span data-ttu-id="09715-105">Methode</span><span class="sxs-lookup"><span data-stu-id="09715-105">Method</span></span>|<span data-ttu-id="09715-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09715-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09715-107">EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="09715-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="09715-108">Ruft eine [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) Instanz, die auf diesem Computer ausgeführt verwalteten Prozesse enthält.</span><span class="sxs-lookup"><span data-stu-id="09715-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="09715-109">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="09715-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="09715-110">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="09715-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09715-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09715-111">Requirements</span></span>  
 <span data-ttu-id="09715-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09715-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09715-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="09715-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="09715-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09715-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09715-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09715-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09715-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09715-116">See also</span></span>
- [<span data-ttu-id="09715-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="09715-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="09715-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="09715-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
