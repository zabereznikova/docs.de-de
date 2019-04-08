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
ms.openlocfilehash: 7581d68f5c2b575403ddc84d06147f012e7ab39e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076340"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="38aec-102">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38aec-102">ICorPublish Interface</span></span>
<span data-ttu-id="38aec-103">Fungiert als allgemeine Schnittstelle für die Veröffentlichung von Informationen zu Prozessen und Informationen zu den Anwendungsdomänen in diesen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="38aec-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38aec-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="38aec-104">Methods</span></span>  
  
|<span data-ttu-id="38aec-105">Methode</span><span class="sxs-lookup"><span data-stu-id="38aec-105">Method</span></span>|<span data-ttu-id="38aec-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38aec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38aec-107">EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="38aec-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="38aec-108">Ruft eine [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) Instanz, die auf diesem Computer ausgeführt verwalteten Prozesse enthält.</span><span class="sxs-lookup"><span data-stu-id="38aec-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="38aec-109">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="38aec-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="38aec-110">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="38aec-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38aec-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38aec-111">Requirements</span></span>  
 <span data-ttu-id="38aec-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38aec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38aec-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="38aec-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="38aec-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38aec-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="38aec-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="38aec-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38aec-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38aec-116">See also</span></span>

- [<span data-ttu-id="38aec-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="38aec-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="38aec-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="38aec-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
