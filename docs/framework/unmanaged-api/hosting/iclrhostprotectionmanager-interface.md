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
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714158"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="67ba6-102">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67ba6-102">ICLRHostProtectionManager Interface</span></span>

<span data-ttu-id="67ba6-103">Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="67ba6-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67ba6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="67ba6-104">Methods</span></span>  
  
|<span data-ttu-id="67ba6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="67ba6-105">Method</span></span>|<span data-ttu-id="67ba6-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="67ba6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67ba6-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="67ba6-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="67ba6-108">Bietet eine Garantie, dass bestimmte seltene Racebedingungen, die zu schwerwiegenden Common Language Runtime (CLR) führen können, nie auftreten.</span><span class="sxs-lookup"><span data-stu-id="67ba6-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="67ba6-109">SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="67ba6-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="67ba6-110">Gibt die Kategorien verwalteter Typen und Member an, deren Ausführung in teilweise vertrauenswürdigem Code blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="67ba6-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67ba6-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67ba6-111">Requirements</span></span>  

 <span data-ttu-id="67ba6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67ba6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67ba6-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="67ba6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67ba6-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="67ba6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67ba6-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67ba6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ba6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67ba6-116">See also</span></span>

- [<span data-ttu-id="67ba6-117">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="67ba6-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="67ba6-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67ba6-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
