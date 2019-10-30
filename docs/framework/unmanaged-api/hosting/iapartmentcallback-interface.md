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
ms.openlocfilehash: 4424509c16dd1d9f83db117ae7343fa03995297e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126909"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="49cb6-102">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49cb6-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="49cb6-103">Stellt Methoden bereit, um Rückrufe in einem Apartment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49cb6-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="49cb6-104">Ein *Apartment* ist ein logischer Container innerhalb eines Prozesses für-Objekte, die die gleichen Thread Zugriffs Anforderungen haben.</span><span class="sxs-lookup"><span data-stu-id="49cb6-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49cb6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="49cb6-105">Methods</span></span>  
  
|<span data-ttu-id="49cb6-106">Methode</span><span class="sxs-lookup"><span data-stu-id="49cb6-106">Method</span></span>|<span data-ttu-id="49cb6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49cb6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49cb6-108">DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="49cb6-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="49cb6-109">Führt die angegebene Funktion in einem Apartment aus.</span><span class="sxs-lookup"><span data-stu-id="49cb6-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49cb6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49cb6-110">Requirements</span></span>  
 <span data-ttu-id="49cb6-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49cb6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49cb6-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="49cb6-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49cb6-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="49cb6-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49cb6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cb6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49cb6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49cb6-115">See also</span></span>

- [<span data-ttu-id="49cb6-116">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="49cb6-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
