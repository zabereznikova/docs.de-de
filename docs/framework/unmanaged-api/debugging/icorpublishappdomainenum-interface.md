---
title: ICorPublishAppDomainEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum
helpviewer_keywords: ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f84a93053744f059eb3fdd06e2fb69e098e24ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="670a6-102">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="670a6-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="670a6-103">Eine Unterklasse von der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Schnittstelle mit Methoden zum Durchlaufen einer Auflistung von Ereignissen [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) Objekte, die derzeit innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="670a6-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="670a6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="670a6-104">Methods</span></span>  
  
|<span data-ttu-id="670a6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="670a6-105">Method</span></span>|<span data-ttu-id="670a6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="670a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="670a6-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="670a6-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="670a6-108">Ruft die angegebene Anzahl von `ICorPublishAppDomain` Instanzen aus der Auflistung, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="670a6-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="670a6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="670a6-109">Remarks</span></span>  
 <span data-ttu-id="670a6-110">Die `ICorPublishAppDomainEnum` -Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670a6-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="670a6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="670a6-111">Requirements</span></span>  
 <span data-ttu-id="670a6-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="670a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="670a6-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="670a6-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="670a6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="670a6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="670a6-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="670a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="670a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="670a6-116">See Also</span></span>  
 [<span data-ttu-id="670a6-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="670a6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="670a6-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="670a6-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
