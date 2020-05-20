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
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703844"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="c0afd-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0afd-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="c0afd-103">Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="c0afd-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0afd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c0afd-104">Methods</span></span>  
  
|<span data-ttu-id="c0afd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c0afd-105">Method</span></span>|<span data-ttu-id="c0afd-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c0afd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0afd-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="c0afd-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="c0afd-108">Bietet eine Garantie, dass bestimmte seltene Racebedingungen, die zu schwerwiegenden Common Language Runtime (CLR) führen können, nie auftreten.</span><span class="sxs-lookup"><span data-stu-id="c0afd-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="c0afd-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="c0afd-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="c0afd-110">Gibt die Kategorien verwalteter Typen und Member an, deren Ausführung in teilweise vertrauenswürdigem Code blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0afd-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0afd-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0afd-111">Requirements</span></span>  
 <span data-ttu-id="c0afd-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0afd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0afd-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c0afd-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0afd-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0afd-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0afd-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0afd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0afd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0afd-116">See also</span></span>

- [<span data-ttu-id="c0afd-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c0afd-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="c0afd-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0afd-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
