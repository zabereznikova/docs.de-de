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
ms.openlocfilehash: 8eb3bd2da9529a681f7f3a09ef7eb78c776cc302
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublish-interface"></a><span data-ttu-id="b3306-102">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3306-102">ICorPublish Interface</span></span>
<span data-ttu-id="b3306-103">Fungiert als allgemeine Schnittstelle für die Veröffentlichung von Informationen zu Prozessen und Informationen zu Anwendungsdomänen in diesen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="b3306-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3306-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b3306-104">Methods</span></span>  
  
|<span data-ttu-id="b3306-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b3306-105">Method</span></span>|<span data-ttu-id="b3306-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3306-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3306-107">EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="b3306-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="b3306-108">Ruft eine [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) Instanz, die die verwalteten Prozesse auf diesem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="b3306-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="b3306-109">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="b3306-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="b3306-110">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="b3306-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3306-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3306-111">Requirements</span></span>  
 <span data-ttu-id="b3306-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3306-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3306-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b3306-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b3306-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3306-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3306-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3306-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3306-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3306-116">See Also</span></span>  
 [<span data-ttu-id="b3306-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b3306-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b3306-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="b3306-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
