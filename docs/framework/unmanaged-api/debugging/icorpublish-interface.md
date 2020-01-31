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
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790725"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="10b70-102">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10b70-102">ICorPublish Interface</span></span>
<span data-ttu-id="10b70-103">Dient als allgemeine Schnittstelle zum Veröffentlichen von Informationen zu Prozessen und Informationen zu den Anwendungs Domänen in diesen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="10b70-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10b70-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10b70-104">Methods</span></span>  
  
|<span data-ttu-id="10b70-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="10b70-105">Method</span></span>|<span data-ttu-id="10b70-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10b70-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10b70-107">EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="10b70-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="10b70-108">Ruft eine [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz ab, die die verwalteten Prozesse enthält, die auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="10b70-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="10b70-109">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="10b70-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="10b70-110">Ruft eine [ICorPublishProcess](icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="10b70-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10b70-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10b70-111">Requirements</span></span>  
 <span data-ttu-id="10b70-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10b70-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10b70-113">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="10b70-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="10b70-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10b70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10b70-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10b70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b70-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10b70-116">See also</span></span>

- [<span data-ttu-id="10b70-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10b70-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="10b70-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="10b70-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
