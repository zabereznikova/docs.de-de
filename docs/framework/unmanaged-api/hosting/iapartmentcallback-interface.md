---
title: IApartmentCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: 0f38314df766b74164bf5e98d9b2153d2dddbcc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721737"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="fcd05-102">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcd05-102">IApartmentCallback Interface</span></span>

<span data-ttu-id="fcd05-103">Stellt Methoden bereit, um Rückrufe in einem Apartment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcd05-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="fcd05-104">Ein *Apartment* ist ein logischer Container innerhalb eines Prozesses für-Objekte, die die gleichen Thread Zugriffs Anforderungen haben.</span><span class="sxs-lookup"><span data-stu-id="fcd05-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcd05-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fcd05-105">Methods</span></span>  
  
|<span data-ttu-id="fcd05-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fcd05-106">Method</span></span>|<span data-ttu-id="fcd05-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fcd05-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcd05-108">DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="fcd05-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="fcd05-109">Führt die angegebene Funktion in einem Apartment aus.</span><span class="sxs-lookup"><span data-stu-id="fcd05-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcd05-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fcd05-110">Requirements</span></span>  

 <span data-ttu-id="fcd05-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcd05-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd05-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fcd05-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcd05-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fcd05-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcd05-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd05-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcd05-115">See also</span></span>

- [<span data-ttu-id="fcd05-116">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcd05-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
