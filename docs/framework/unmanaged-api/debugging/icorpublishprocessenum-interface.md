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
ms.openlocfilehash: ebf484524b32d8e917d88c21425fab314dfc41be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692617"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="8e3bc-102">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e3bc-102">ICorPublishProcessEnum Interface</span></span>

<span data-ttu-id="8e3bc-103">Eine Unterklasse der [ICorPublishEnum](icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishProcess](icorpublishprocess-interface.md) -Objekten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e3bc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8e3bc-104">Methods</span></span>  
  
|<span data-ttu-id="8e3bc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8e3bc-105">Method</span></span>|<span data-ttu-id="8e3bc-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e3bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e3bc-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="8e3bc-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="8e3bc-108">Ruft die angegebene Anzahl von- `ICorPublishProcess` Instanzen ab der aktuellen Position aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e3bc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e3bc-109">Remarks</span></span>  

 <span data-ttu-id="8e3bc-110">Die- `ICorPublishProcessEnum` Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8e3bc-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="8e3bc-111">Eine `ICorPublishProcessEnum` Instanz wird von der [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="8e3bc-112">Der Durchlauf der Auflistung von `ICorPublishProcess` Objekten basiert auf den Filterkriterien, die zum Zeitpunkt der `ICorPublishProcessEnum` Erstellung der Instanz angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e3bc-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8e3bc-113">Requirements</span></span>  

 <span data-ttu-id="8e3bc-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e3bc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e3bc-115">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="8e3bc-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8e3bc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e3bc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e3bc-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e3bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3bc-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e3bc-118">See also</span></span>

- [<span data-ttu-id="8e3bc-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8e3bc-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8e3bc-120">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="8e3bc-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
