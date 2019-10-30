---
title: ICorPublishProcessEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103415"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="006f8-102">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="006f8-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="006f8-103">Eine Unterklasse der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Objekten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="006f8-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="006f8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="006f8-104">Methods</span></span>  
  
|<span data-ttu-id="006f8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="006f8-105">Method</span></span>|<span data-ttu-id="006f8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="006f8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="006f8-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="006f8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="006f8-108">Ruft die angegebene Anzahl von `ICorPublishProcess` Instanzen ab der aktuellen Position aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="006f8-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="006f8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="006f8-109">Remarks</span></span>  
 <span data-ttu-id="006f8-110">Die `ICorPublishProcessEnum`-Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="006f8-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="006f8-111">Eine `ICorPublishProcessEnum`-Instanz wird von der [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="006f8-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="006f8-112">Der Durchlauf der Auflistung von `ICorPublishProcess` Objekten basiert auf den Filterkriterien, die zum Zeitpunkt der Erstellung der `ICorPublishProcessEnum` Instanz angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="006f8-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="006f8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="006f8-113">Requirements</span></span>  
 <span data-ttu-id="006f8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="006f8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="006f8-115">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="006f8-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="006f8-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="006f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="006f8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="006f8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006f8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="006f8-118">See also</span></span>

- [<span data-ttu-id="006f8-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="006f8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="006f8-120">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="006f8-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
