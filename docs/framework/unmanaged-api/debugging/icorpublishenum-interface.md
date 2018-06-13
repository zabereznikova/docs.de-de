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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3536184fa7798ac8eabe851221ec692c126460b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424013"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="fee15-102">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fee15-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="fee15-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die die Veröffentlichung von Informationen über Prozesse und Anwendungsdomänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fee15-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fee15-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fee15-104">Methods</span></span>  
  
|<span data-ttu-id="fee15-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fee15-105">Method</span></span>|<span data-ttu-id="fee15-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fee15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fee15-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="fee15-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="fee15-108">Erstellt eine Kopie dieser `ICorPublishEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="fee15-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="fee15-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="fee15-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="fee15-110">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="fee15-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="fee15-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="fee15-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="fee15-112">Verschiebt den Cursor auf den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="fee15-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="fee15-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="fee15-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="fee15-114">Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="fee15-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fee15-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fee15-115">Remarks</span></span>  
 <span data-ttu-id="fee15-116">Die folgenden Enumeratoren leiten sich von `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="fee15-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="fee15-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="fee15-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="fee15-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="fee15-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="fee15-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fee15-119">Requirements</span></span>  
 <span data-ttu-id="fee15-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fee15-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fee15-121">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fee15-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fee15-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fee15-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fee15-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fee15-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee15-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fee15-124">See Also</span></span>  
 [<span data-ttu-id="fee15-125">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="fee15-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [<span data-ttu-id="fee15-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fee15-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
