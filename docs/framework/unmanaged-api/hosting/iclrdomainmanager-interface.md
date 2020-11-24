---
title: ICLRDomainManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681170"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="76640-102">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76640-102">ICLRDomainManager Interface</span></span>

<span data-ttu-id="76640-103">Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="76640-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76640-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="76640-104">Methods</span></span>  
  
|<span data-ttu-id="76640-105">Methode</span><span class="sxs-lookup"><span data-stu-id="76640-105">Method</span></span>|<span data-ttu-id="76640-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76640-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76640-107">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="76640-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="76640-108">Gibt den von der-Klasse abgeleiteten Typ <xref:System.AppDomainManager?displayProperty=nameWithType> des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="76640-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="76640-109">SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="76640-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="76640-110">Legt Eigenschaften fest, die verwendet werden, um die Standard Anwendungsdomäne zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="76640-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76640-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76640-111">Remarks</span></span>  

 <span data-ttu-id="76640-112">Um eine Instanz dieser Schnittstelle abzurufen, wenden Sie die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode mit dem Manager-Typ IID an `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="76640-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76640-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="76640-113">Requirements</span></span>  

 <span data-ttu-id="76640-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76640-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76640-115">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="76640-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="76640-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="76640-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76640-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76640-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76640-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76640-118">See also</span></span>

- [<span data-ttu-id="76640-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="76640-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="76640-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="76640-120">Hosting</span></span>](index.md)
