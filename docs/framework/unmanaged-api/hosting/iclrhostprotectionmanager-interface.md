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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944666"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="6822c-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6822c-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="6822c-103">Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder aus, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6822c-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6822c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6822c-104">Methods</span></span>  
  
|<span data-ttu-id="6822c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6822c-105">Method</span></span>|<span data-ttu-id="6822c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6822c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6822c-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="6822c-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="6822c-108">Gewährleistet, dass bestimmte seltenen Racebedingungen, die schwerwiegenden common Language Runtime (CLR)-Fehler verursachen können, niemals auftreten.</span><span class="sxs-lookup"><span data-stu-id="6822c-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="6822c-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="6822c-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="6822c-110">Gibt die Kategorien von verwalteten Typen und Member, die blockiert, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6822c-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6822c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6822c-111">Requirements</span></span>  
 <span data-ttu-id="6822c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6822c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6822c-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6822c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6822c-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6822c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6822c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6822c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6822c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6822c-116">See also</span></span>

- [<span data-ttu-id="6822c-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6822c-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="6822c-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6822c-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
