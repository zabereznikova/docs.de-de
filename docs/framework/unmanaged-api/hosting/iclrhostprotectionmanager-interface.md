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
ms.openlocfilehash: c630fcd4667c8b19c4e21335549674d32508e439
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432835"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="74c10-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74c10-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="74c10-103">Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder in teilweise vertrauenswürdigem Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74c10-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74c10-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="74c10-104">Methods</span></span>  
  
|<span data-ttu-id="74c10-105">Methode</span><span class="sxs-lookup"><span data-stu-id="74c10-105">Method</span></span>|<span data-ttu-id="74c10-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74c10-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74c10-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="74c10-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="74c10-108">Gewährleistet, dass bestimmte seltenen Racebedingungen, die schwerwiegende common Language Runtime (CLR)-Fehler führen können, niemals auftreten.</span><span class="sxs-lookup"><span data-stu-id="74c10-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="74c10-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="74c10-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="74c10-110">Gibt die Kategorien von verwalteten Typen und Membern, die ausführen in teilweise vertrauenswürdigem Code gesperrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="74c10-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74c10-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74c10-111">Requirements</span></span>  
 <span data-ttu-id="74c10-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c10-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c10-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74c10-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74c10-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="74c10-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74c10-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74c10-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c10-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74c10-116">See Also</span></span>  
 [<span data-ttu-id="74c10-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="74c10-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="74c10-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74c10-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
