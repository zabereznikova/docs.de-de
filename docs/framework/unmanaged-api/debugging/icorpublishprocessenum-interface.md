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
ms.openlocfilehash: dd71a2bd4a52da8fa77592363e2eb7c8f5101fd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423984"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="66bc0-102">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66bc0-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="66bc0-103">Eine Unterklasse von der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Schnittstelle mit Methoden zum Durchlaufen einer Auflistung von Ereignissen [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="66bc0-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66bc0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="66bc0-104">Methods</span></span>  
  
|<span data-ttu-id="66bc0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="66bc0-105">Method</span></span>|<span data-ttu-id="66bc0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66bc0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66bc0-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="66bc0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="66bc0-108">Ruft die angegebene Anzahl von `ICorPublishProcess` Instanzen aus der Auflistung, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="66bc0-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66bc0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66bc0-109">Remarks</span></span>  
 <span data-ttu-id="66bc0-110">Die `ICorPublishProcessEnum` -Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="66bc0-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="66bc0-111">Ein `ICorPublishProcessEnum` Instanz wird erstellt, indem die [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="66bc0-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="66bc0-112">Das Durchlaufen der Auflistung von `ICorPublishProcess` Objekten basiert auf den Filterkriterien zum Zeitpunkt der `ICorPublishProcessEnum` Instanz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="66bc0-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66bc0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66bc0-113">Requirements</span></span>  
 <span data-ttu-id="66bc0-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66bc0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66bc0-115">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="66bc0-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="66bc0-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66bc0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66bc0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bc0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bc0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66bc0-118">See Also</span></span>  
 [<span data-ttu-id="66bc0-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="66bc0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="66bc0-120">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="66bc0-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
