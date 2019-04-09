---
title: ICLRHostProtectionManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177774"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="c7dce-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7dce-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="c7dce-103">Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder aus, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7dce-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7dce-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c7dce-104">Methods</span></span>  
  
|<span data-ttu-id="c7dce-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c7dce-105">Method</span></span>|<span data-ttu-id="c7dce-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7dce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7dce-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="c7dce-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="c7dce-108">Gewährleistet, dass bestimmte seltenen Racebedingungen, die schwerwiegenden common Language Runtime (CLR)-Fehler verursachen können, niemals auftreten.</span><span class="sxs-lookup"><span data-stu-id="c7dce-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="c7dce-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="c7dce-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="c7dce-110">Gibt die Kategorien von verwalteten Typen und Member, die blockiert, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7dce-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7dce-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7dce-111">Requirements</span></span>  
 <span data-ttu-id="c7dce-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7dce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7dce-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7dce-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7dce-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c7dce-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c7dce-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c7dce-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7dce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7dce-116">See also</span></span>

- [<span data-ttu-id="c7dce-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c7dce-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="c7dce-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7dce-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
