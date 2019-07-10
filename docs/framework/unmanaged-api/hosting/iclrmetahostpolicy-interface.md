---
title: ICLRMetaHostPolicy-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a34a8f185ce600f4792cf05c3e95623b70ad6c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776535"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="fbd16-102">ICLRMetaHostPolicy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbd16-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="fbd16-103">Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode, die einen Zeiger auf eine common Language Runtime (CLR)-Schnittstelle basierend auf einer Richtlinienkriterien zurückgibt, verwalteten Assembly, Version und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fbd16-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbd16-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fbd16-104">Methods</span></span>  
  
|<span data-ttu-id="fbd16-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fbd16-105">Method</span></span>|<span data-ttu-id="fbd16-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbd16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbd16-107">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="fbd16-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="fbd16-108">Bietet eine bevorzugte CLR-Schnittstelle auf der Grundlage einer Richtlinienkriterien, einer verwalteten Assembly, Version und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fbd16-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbd16-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fbd16-109">Remarks</span></span>  
 <span data-ttu-id="fbd16-110">Sie erhalten einen Verweis auf diese Schnittstelle durch Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fbd16-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="fbd16-111">Diese Schnittstelle nicht lädt oder aktiviert die CLR, sondern einfach gibt die bevorzugte CLR-Version anhand der verfügbaren Versionen, die installiert oder geladen werden.</span><span class="sxs-lookup"><span data-stu-id="fbd16-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="fbd16-112">Die .NET Framework 4-hosting-API konsolidiert Richtlinien an, sodass Hosts mit bestimmten Anforderungen an die grundlegenden Funktionen verwenden können, ohne dass unbeabsichtigte Folge haben.</span><span class="sxs-lookup"><span data-stu-id="fbd16-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="fbd16-113">Viele der Exporte "Mscoree.dll" werden z. B. auf eine bestimmte CLR binden, obwohl es sich bei eine Methode nicht logisch erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fbd16-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="fbd16-114">Die [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) Enumeration bietet Bindungsrichtlinien für die, die für die Mehrzahl der Hosts gelten.</span><span class="sxs-lookup"><span data-stu-id="fbd16-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbd16-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbd16-115">Requirements</span></span>  
 <span data-ttu-id="fbd16-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbd16-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbd16-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fbd16-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbd16-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fbd16-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbd16-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbd16-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd16-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd16-120">See also</span></span>

- [<span data-ttu-id="fbd16-121">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fbd16-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="fbd16-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fbd16-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fbd16-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="fbd16-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
