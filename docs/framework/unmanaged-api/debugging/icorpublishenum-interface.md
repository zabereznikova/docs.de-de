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
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160133"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="6109c-102">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6109c-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="6109c-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die die Veröffentlichung von Informationen zu Prozessen und Anwendungsdomänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6109c-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6109c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6109c-104">Methods</span></span>  
  
|<span data-ttu-id="6109c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6109c-105">Method</span></span>|<span data-ttu-id="6109c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6109c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6109c-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="6109c-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="6109c-108">Erstellt eine Kopie dieses `ICorPublishEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="6109c-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="6109c-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="6109c-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="6109c-110">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="6109c-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="6109c-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="6109c-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="6109c-112">Verschiebt den Cursor auf den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="6109c-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="6109c-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="6109c-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="6109c-114">Verschiebt den Cursor vorwärts in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="6109c-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6109c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6109c-115">Remarks</span></span>  
 <span data-ttu-id="6109c-116">Leiten Sie die folgenden Enumeratoren von `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="6109c-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="6109c-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6109c-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="6109c-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="6109c-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="6109c-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6109c-119">Requirements</span></span>  
 <span data-ttu-id="6109c-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6109c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6109c-121">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6109c-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6109c-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6109c-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6109c-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6109c-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6109c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6109c-124">See also</span></span>

- [<span data-ttu-id="6109c-125">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="6109c-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="6109c-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6109c-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
