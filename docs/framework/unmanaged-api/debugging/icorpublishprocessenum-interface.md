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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5186df61eb82b29fcfa9776408498b748068e122
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173653"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="ed7cc-102">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed7cc-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="ed7cc-103">Eine Unterklasse von der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von bietet [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="ed7cc-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed7cc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed7cc-104">Methods</span></span>  
  
|<span data-ttu-id="ed7cc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ed7cc-105">Method</span></span>|<span data-ttu-id="ed7cc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed7cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed7cc-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="ed7cc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="ed7cc-108">Ruft die angegebene Anzahl von `ICorPublishProcess` Instanzen aus der Auflistung, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="ed7cc-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed7cc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed7cc-109">Remarks</span></span>  
 <span data-ttu-id="ed7cc-110">Die `ICorPublishProcessEnum` -Schnittstelle implementiert die Methoden der abstrakten Schnittstelle, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ed7cc-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="ed7cc-111">Ein `ICorPublishProcessEnum` Instanz wird erstellt, indem die [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ed7cc-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="ed7cc-112">Das Durchlaufen der Auflistung von `ICorPublishProcess` Objekten basiert auf den Filterkriterien zum Zeitpunkt der `ICorPublishProcessEnum` Instanz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed7cc-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed7cc-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed7cc-113">Requirements</span></span>  
 <span data-ttu-id="ed7cc-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed7cc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7cc-115">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ed7cc-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ed7cc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed7cc-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ed7cc-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ed7cc-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed7cc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed7cc-118">See also</span></span>

- [<span data-ttu-id="ed7cc-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ed7cc-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ed7cc-120">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="ed7cc-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
