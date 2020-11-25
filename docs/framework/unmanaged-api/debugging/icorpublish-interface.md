---
title: ICorPublish-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 3ff4efe8b3e2932da7f65246bf4ad614a4dd86cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694411"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="a8962-102">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8962-102">ICorPublish Interface</span></span>

<span data-ttu-id="a8962-103">Dient als allgemeine Schnittstelle zum Veröffentlichen von Informationen zu Prozessen und Informationen zu den Anwendungs Domänen in diesen Prozessen.</span><span class="sxs-lookup"><span data-stu-id="a8962-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8962-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a8962-104">Methods</span></span>  
  
|<span data-ttu-id="a8962-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a8962-105">Method</span></span>|<span data-ttu-id="a8962-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a8962-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8962-107">EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="a8962-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="a8962-108">Ruft eine [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz ab, die die verwalteten Prozesse enthält, die auf diesem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a8962-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="a8962-109">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="a8962-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="a8962-110">Ruft eine [ICorPublishProcess](icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="a8962-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8962-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a8962-111">Requirements</span></span>  

 <span data-ttu-id="a8962-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8962-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8962-113">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="a8962-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a8962-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8962-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8962-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8962-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8962-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8962-116">See also</span></span>

- [<span data-ttu-id="a8962-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a8962-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a8962-118">CorpubPublish-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="a8962-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
