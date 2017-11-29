---
title: IApartmentCallback-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d2f2ea73da2273ff6f0abb725ec3e3fb8ca79ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="68f8a-102">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68f8a-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="68f8a-103">Stellt Methoden für Rückrufe innerhalb eines Apartments bereit.</span><span class="sxs-lookup"><span data-stu-id="68f8a-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="68f8a-104">Ein *Apartment* ist ein logischer Container innerhalb eines Prozesses für Objekte, die die Anforderungen der gleichen Thread freigeben.</span><span class="sxs-lookup"><span data-stu-id="68f8a-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68f8a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="68f8a-105">Methods</span></span>  
  
|<span data-ttu-id="68f8a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="68f8a-106">Method</span></span>|<span data-ttu-id="68f8a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68f8a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68f8a-108">DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="68f8a-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="68f8a-109">Führt die angegebene Funktion innerhalb eines Apartments aus.</span><span class="sxs-lookup"><span data-stu-id="68f8a-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68f8a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68f8a-110">Requirements</span></span>  
 <span data-ttu-id="68f8a-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68f8a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68f8a-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68f8a-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68f8a-113">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68f8a-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68f8a-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68f8a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f8a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68f8a-115">See Also</span></span>  
 [<span data-ttu-id="68f8a-116">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="68f8a-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
