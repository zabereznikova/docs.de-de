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
ms.openlocfilehash: 610f62274aea88c1d5f9bbe1456685aa1d3bca68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423740"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="8d723-102">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d723-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="8d723-103">Eine Unterklasse von der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Schnittstelle mit Methoden zum Durchlaufen einer Auflistung von Ereignissen [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) Objekte, die derzeit innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8d723-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d723-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8d723-104">Methods</span></span>  
  
|<span data-ttu-id="8d723-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8d723-105">Method</span></span>|<span data-ttu-id="8d723-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d723-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d723-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="8d723-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="8d723-108">Ruft die angegebene Anzahl von `ICorPublishAppDomain` Instanzen aus der Auflistung, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="8d723-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d723-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d723-109">Remarks</span></span>  
 <span data-ttu-id="8d723-110">Die `ICorPublishAppDomainEnum` -Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8d723-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d723-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d723-111">Requirements</span></span>  
 <span data-ttu-id="8d723-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d723-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d723-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8d723-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8d723-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d723-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d723-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d723-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d723-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d723-116">See Also</span></span>  
 [<span data-ttu-id="8d723-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8d723-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8d723-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="8d723-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
