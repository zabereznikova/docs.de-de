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
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790673"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="53c9f-102">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53c9f-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="53c9f-103">Eine Unterklasse der [ICorPublishEnum](icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishAppDomain](icorpublishappdomain-interface.md) -Objekten bereitstellt, die derzeit in einem Prozess vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="53c9f-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53c9f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="53c9f-104">Methods</span></span>  
  
|<span data-ttu-id="53c9f-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="53c9f-105">Method</span></span>|<span data-ttu-id="53c9f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53c9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53c9f-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="53c9f-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="53c9f-108">Ruft die angegebene Anzahl von `ICorPublishAppDomain` Instanzen ab der aktuellen Position aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="53c9f-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53c9f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53c9f-109">Remarks</span></span>  
 <span data-ttu-id="53c9f-110">Die `ICorPublishAppDomainEnum`-Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="53c9f-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53c9f-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53c9f-111">Requirements</span></span>  
 <span data-ttu-id="53c9f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53c9f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53c9f-113">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="53c9f-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="53c9f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53c9f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53c9f-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53c9f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c9f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53c9f-116">See also</span></span>

- [<span data-ttu-id="53c9f-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="53c9f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="53c9f-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="53c9f-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
