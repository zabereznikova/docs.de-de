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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffa06fd42b5cfa09817bae9f0b3a3810e30f99c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430966"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="3cfb2-102">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cfb2-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="3cfb2-103">Stellt Methoden für Rückrufe innerhalb eines Apartments bereit.</span><span class="sxs-lookup"><span data-stu-id="3cfb2-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="3cfb2-104">Ein *Apartment* ist ein logischer Container innerhalb eines Prozesses für Objekte, die die Anforderungen der gleichen Thread freigeben.</span><span class="sxs-lookup"><span data-stu-id="3cfb2-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3cfb2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3cfb2-105">Methods</span></span>  
  
|<span data-ttu-id="3cfb2-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3cfb2-106">Method</span></span>|<span data-ttu-id="3cfb2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cfb2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3cfb2-108">DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="3cfb2-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="3cfb2-109">Führt die angegebene Funktion innerhalb eines Apartments aus.</span><span class="sxs-lookup"><span data-stu-id="3cfb2-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cfb2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3cfb2-110">Requirements</span></span>  
 <span data-ttu-id="3cfb2-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfb2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfb2-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3cfb2-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cfb2-113">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3cfb2-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cfb2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cfb2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cfb2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cfb2-115">See Also</span></span>  
 [<span data-ttu-id="3cfb2-116">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3cfb2-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
