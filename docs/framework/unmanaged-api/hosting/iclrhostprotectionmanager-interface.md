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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177774"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="aa473-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa473-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="aa473-103">Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder aus, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa473-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa473-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="aa473-104">Methods</span></span>  
  
|<span data-ttu-id="aa473-105">Methode</span><span class="sxs-lookup"><span data-stu-id="aa473-105">Method</span></span>|<span data-ttu-id="aa473-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa473-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa473-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="aa473-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="aa473-108">Gewährleistet, dass bestimmte seltenen Racebedingungen, die schwerwiegenden common Language Runtime (CLR)-Fehler verursachen können, niemals auftreten.</span><span class="sxs-lookup"><span data-stu-id="aa473-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="aa473-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="aa473-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="aa473-110">Gibt die Kategorien von verwalteten Typen und Member, die blockiert, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa473-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa473-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa473-111">Requirements</span></span>  
 <span data-ttu-id="aa473-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa473-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa473-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aa473-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa473-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="aa473-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa473-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa473-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa473-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa473-116">See also</span></span>

- [<span data-ttu-id="aa473-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="aa473-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="aa473-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa473-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
