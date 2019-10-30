---
title: ICorPublishEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103461"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="f17f9-102">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f17f9-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="f17f9-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die bei der Veröffentlichung von Informationen zu Prozessen und Anwendungs Domänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f17f9-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f17f9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f17f9-104">Methods</span></span>  
  
|<span data-ttu-id="f17f9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f17f9-105">Method</span></span>|<span data-ttu-id="f17f9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f17f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f17f9-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="f17f9-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="f17f9-108">Erstellt eine Kopie dieses `ICorPublishEnum` Objekts.</span><span class="sxs-lookup"><span data-stu-id="f17f9-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="f17f9-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="f17f9-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="f17f9-110">Ruft die Anzahl der Elemente in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="f17f9-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="f17f9-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="f17f9-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="f17f9-112">Verschiebt den Cursor von an den Anfang der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="f17f9-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="f17f9-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="f17f9-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="f17f9-114">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="f17f9-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f17f9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f17f9-115">Remarks</span></span>  
 <span data-ttu-id="f17f9-116">Die folgenden Enumeratoren werden von `ICorPublishEnum`abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="f17f9-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="f17f9-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="f17f9-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="f17f9-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="f17f9-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="f17f9-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f17f9-119">Requirements</span></span>  
 <span data-ttu-id="f17f9-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f17f9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f17f9-121">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="f17f9-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f17f9-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f17f9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f17f9-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f17f9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17f9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f17f9-124">See also</span></span>

- [<span data-ttu-id="f17f9-125">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="f17f9-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="f17f9-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f17f9-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
