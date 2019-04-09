---
title: ICorPublishAppDomainEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f6d4af7c01f91dff77d6ba715ef845f523c7fb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090029"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="7c8bc-102">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c8bc-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="7c8bc-103">Eine Unterklasse von der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von bietet [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) Objekte, die gerade innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7c8bc-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c8bc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c8bc-104">Methods</span></span>  
  
|<span data-ttu-id="7c8bc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7c8bc-105">Method</span></span>|<span data-ttu-id="7c8bc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c8bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c8bc-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="7c8bc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="7c8bc-108">Ruft die angegebene Anzahl von `ICorPublishAppDomain` Instanzen aus der Auflistung, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="7c8bc-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c8bc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c8bc-109">Remarks</span></span>  
 <span data-ttu-id="7c8bc-110">Die `ICorPublishAppDomainEnum` -Schnittstelle implementiert die Methoden der abstrakten Schnittstelle, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7c8bc-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c8bc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c8bc-111">Requirements</span></span>  
 <span data-ttu-id="7c8bc-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c8bc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8bc-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7c8bc-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7c8bc-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c8bc-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7c8bc-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7c8bc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c8bc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c8bc-116">See also</span></span>

- [<span data-ttu-id="7c8bc-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c8bc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7c8bc-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="7c8bc-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
