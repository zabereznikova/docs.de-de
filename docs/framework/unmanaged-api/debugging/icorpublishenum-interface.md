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
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790623"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="0bf99-102">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bf99-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="0bf99-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die bei der Veröffentlichung von Informationen zu Prozessen und Anwendungs Domänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bf99-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bf99-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0bf99-104">Methods</span></span>  
  
|<span data-ttu-id="0bf99-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="0bf99-105">Method</span></span>|<span data-ttu-id="0bf99-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bf99-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="0bf99-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="0bf99-108">Erstellt eine Kopie dieses `ICorPublishEnum` Objekts.</span><span class="sxs-lookup"><span data-stu-id="0bf99-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="0bf99-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="0bf99-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="0bf99-110">Ruft die Anzahl der Elemente in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="0bf99-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="0bf99-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="0bf99-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="0bf99-112">Verschiebt den Cursor von an den Anfang der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0bf99-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="0bf99-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="0bf99-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="0bf99-114">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="0bf99-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bf99-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bf99-115">Remarks</span></span>  
 <span data-ttu-id="0bf99-116">Die folgenden Enumeratoren werden von `ICorPublishEnum`abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="0bf99-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="0bf99-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="0bf99-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="0bf99-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="0bf99-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="0bf99-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0bf99-119">Requirements</span></span>  
 <span data-ttu-id="0bf99-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bf99-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf99-121">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="0bf99-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0bf99-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bf99-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bf99-123">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf99-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf99-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bf99-124">See also</span></span>

- [<span data-ttu-id="0bf99-125">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="0bf99-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="0bf99-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0bf99-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
