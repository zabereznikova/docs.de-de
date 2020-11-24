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
ms.openlocfilehash: 492d4b727ce507340fec47d30a791aa49d0cecb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693345"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="0b581-102">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b581-102">ICorPublishEnum Interface</span></span>

<span data-ttu-id="0b581-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die bei der Veröffentlichung von Informationen zu Prozessen und Anwendungs Domänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b581-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b581-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0b581-104">Methods</span></span>  
  
|<span data-ttu-id="0b581-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0b581-105">Method</span></span>|<span data-ttu-id="0b581-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b581-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b581-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="0b581-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="0b581-108">Erstellt eine Kopie dieses `ICorPublishEnum`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="0b581-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="0b581-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="0b581-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="0b581-110">Ruft die Anzahl der Elemente in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="0b581-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="0b581-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="0b581-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="0b581-112">Verschiebt den Cursor von an den Anfang der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b581-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="0b581-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="0b581-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="0b581-114">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="0b581-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b581-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b581-115">Remarks</span></span>  

 <span data-ttu-id="0b581-116">Die folgenden Enumeratoren werden von abgeleitet `ICorPublishEnum` :</span><span class="sxs-lookup"><span data-stu-id="0b581-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="0b581-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="0b581-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="0b581-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="0b581-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="0b581-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b581-119">Requirements</span></span>  

 <span data-ttu-id="0b581-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b581-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b581-121">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="0b581-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0b581-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b581-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b581-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b581-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b581-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b581-124">See also</span></span>

- [<span data-ttu-id="0b581-125">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="0b581-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="0b581-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0b581-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
