---
title: ICorPublish-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish
helpviewer_keywords: ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7769d26d65a97ea8d1b109e0098eae7e7d51ed10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublish-interface"></a><span data-ttu-id="ff1b3-102">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff1b3-102">ICorPublish Interface</span></span>
<span data-ttu-id="ff1b3-103">Fungiert als allgemeine Schnittstelle für die Veröffentlichung von Informationen zu Prozessen und Informationen zu Anwendungsdomänen in diesen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="ff1b3-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff1b3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff1b3-104">Methods</span></span>  
  
|<span data-ttu-id="ff1b3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ff1b3-105">Method</span></span>|<span data-ttu-id="ff1b3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff1b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff1b3-107">EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="ff1b3-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="ff1b3-108">Ruft eine [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) Instanz, die die verwalteten Prozesse auf diesem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="ff1b3-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="ff1b3-109">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="ff1b3-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="ff1b3-110">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff1b3-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff1b3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff1b3-111">Requirements</span></span>  
 <span data-ttu-id="ff1b3-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff1b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff1b3-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ff1b3-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ff1b3-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff1b3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff1b3-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff1b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1b3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff1b3-116">See Also</span></span>  
 [<span data-ttu-id="ff1b3-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff1b3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ff1b3-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="ff1b3-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
