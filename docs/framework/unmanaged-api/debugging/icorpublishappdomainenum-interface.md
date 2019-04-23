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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090029"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="2dd47-102">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2dd47-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="2dd47-103">Eine Unterklasse von der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von bietet [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) Objekte, die gerade innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2dd47-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2dd47-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2dd47-104">Methods</span></span>  
  
|<span data-ttu-id="2dd47-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2dd47-105">Method</span></span>|<span data-ttu-id="2dd47-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2dd47-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2dd47-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2dd47-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="2dd47-108">Ruft die angegebene Anzahl von `ICorPublishAppDomain` Instanzen aus der Auflistung, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="2dd47-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dd47-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2dd47-109">Remarks</span></span>  
 <span data-ttu-id="2dd47-110">Die `ICorPublishAppDomainEnum` -Schnittstelle implementiert die Methoden der abstrakten Schnittstelle, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2dd47-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd47-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2dd47-111">Requirements</span></span>  
 <span data-ttu-id="2dd47-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dd47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dd47-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2dd47-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2dd47-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dd47-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dd47-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dd47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd47-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dd47-116">See also</span></span>

- [<span data-ttu-id="2dd47-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2dd47-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2dd47-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="2dd47-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
