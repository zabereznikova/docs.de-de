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
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129804"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="3d330-102">IApartmentCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d330-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="3d330-103">Stellt Methoden für Rückrufe innerhalb einer Apartment.</span><span class="sxs-lookup"><span data-stu-id="3d330-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="3d330-104">Ein *Apartment* ist ein logischer Container innerhalb eines Prozesses für Objekte, die die gleichen Thread zugriffsanforderungen gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="3d330-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d330-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3d330-105">Methods</span></span>  
  
|<span data-ttu-id="3d330-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3d330-106">Method</span></span>|<span data-ttu-id="3d330-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d330-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d330-108">DoCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="3d330-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="3d330-109">Führt die angegebene Funktion innerhalb eines Apartments an.</span><span class="sxs-lookup"><span data-stu-id="3d330-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d330-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d330-110">Requirements</span></span>  
 <span data-ttu-id="3d330-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d330-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d330-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d330-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d330-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3d330-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3d330-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3d330-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d330-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d330-115">See also</span></span>

- [<span data-ttu-id="3d330-116">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3d330-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
