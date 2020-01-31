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
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790498"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="a2fdc-102">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2fdc-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="a2fdc-103">Eine Unterklasse der [ICorPublishEnum](icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishProcess](icorpublishprocess-interface.md) -Objekten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a2fdc-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2fdc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a2fdc-104">Methods</span></span>  
  
|<span data-ttu-id="a2fdc-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="a2fdc-105">Method</span></span>|<span data-ttu-id="a2fdc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2fdc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2fdc-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a2fdc-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="a2fdc-108">Ruft die angegebene Anzahl von `ICorPublishProcess` Instanzen ab der aktuellen Position aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="a2fdc-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2fdc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2fdc-109">Remarks</span></span>  
 <span data-ttu-id="a2fdc-110">Die `ICorPublishProcessEnum`-Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a2fdc-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="a2fdc-111">Eine `ICorPublishProcessEnum`-Instanz wird von der [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="a2fdc-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="a2fdc-112">Der Durchlauf der Auflistung von `ICorPublishProcess` Objekten basiert auf den Filterkriterien, die zum Zeitpunkt der Erstellung der `ICorPublishProcessEnum` Instanz angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a2fdc-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2fdc-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2fdc-113">Requirements</span></span>  
 <span data-ttu-id="a2fdc-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2fdc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2fdc-115">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="a2fdc-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a2fdc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2fdc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2fdc-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2fdc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fdc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2fdc-118">See also</span></span>

- [<span data-ttu-id="a2fdc-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2fdc-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a2fdc-120">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="a2fdc-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
