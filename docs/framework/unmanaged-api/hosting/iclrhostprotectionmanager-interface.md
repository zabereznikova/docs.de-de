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
ms.openlocfilehash: 0487a87420c888cf5466f54c28c2d89623260add
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141051"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="f8325-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8325-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="f8325-103">Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f8325-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8325-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f8325-104">Methods</span></span>  
  
|<span data-ttu-id="f8325-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f8325-105">Method</span></span>|<span data-ttu-id="f8325-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8325-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8325-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="f8325-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="f8325-108">Bietet eine Garantie, dass bestimmte seltene Racebedingungen, die zu schwerwiegenden Common Language Runtime (CLR) führen können, nie auftreten.</span><span class="sxs-lookup"><span data-stu-id="f8325-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="f8325-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="f8325-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="f8325-110">Gibt die Kategorien verwalteter Typen und Member an, deren Ausführung in teilweise vertrauenswürdigem Code blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8325-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8325-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8325-111">Requirements</span></span>  
 <span data-ttu-id="f8325-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8325-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8325-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f8325-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8325-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f8325-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8325-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8325-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8325-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8325-116">See also</span></span>

- [<span data-ttu-id="f8325-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f8325-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="f8325-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8325-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
