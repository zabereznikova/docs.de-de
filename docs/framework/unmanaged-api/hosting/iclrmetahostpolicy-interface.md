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
ms.openlocfilehash: 79b62a5e2aad9cfcd14ba40c1abf0342bfe57a4b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703533"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="1ad48-102">ICLRMetaHostPolicy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ad48-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="1ad48-103">Stellt die [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode bereit, die einen Zeiger auf eine Common Language Runtime (CLR)-Schnittstelle basierend auf einem Richtlinien Kriterium, einer verwalteten Assembly, einer Version und einer Konfigurationsdatei zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1ad48-103">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ad48-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1ad48-104">Methods</span></span>  
  
|<span data-ttu-id="1ad48-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1ad48-105">Method</span></span>|<span data-ttu-id="1ad48-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ad48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ad48-107">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="1ad48-107">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="1ad48-108">Bietet eine bevorzugte CLR-Schnittstelle, die auf Richtlinien Kriterien, verwalteten Assemblys, Versionen und Konfigurationsdateien basiert.</span><span class="sxs-lookup"><span data-stu-id="1ad48-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ad48-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ad48-109">Remarks</span></span>  
 <span data-ttu-id="1ad48-110">Sie können einen Verweis auf diese Schnittstelle abrufen, indem Sie die [CLRCreateInstance](clrcreateinstance-function.md) -Funktion aufrufen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ad48-110">You can get a reference to this interface by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="1ad48-111">Diese Schnittstelle lädt oder aktiviert die CLR nicht, sondern gibt einfach die bevorzugte CLR-Version basierend auf den verfügbaren installierten oder geladenen Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="1ad48-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="1ad48-112">Die .NET Framework 4-Hosting-API konsolidiert Richtlinien, sodass Hosts mit speziellen Anforderungen grundlegende Funktionen verwenden können, ohne dass dabei unbeabsichtigte Strafen anfallen.</span><span class="sxs-lookup"><span data-stu-id="1ad48-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="1ad48-113">Beispielsweise werden viele der Mscoree. dll-Exporte an eine bestimmte CLR gebunden, obwohl eine Methode dies möglicherweise nicht logisch erfordert.</span><span class="sxs-lookup"><span data-stu-id="1ad48-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="1ad48-114">Die [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) -Enumeration stellt Bindungs Richtlinien bereit, die für die Mehrzahl der Hosts üblich sind.</span><span class="sxs-lookup"><span data-stu-id="1ad48-114">The [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ad48-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ad48-115">Requirements</span></span>  
 <span data-ttu-id="1ad48-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ad48-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad48-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="1ad48-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1ad48-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ad48-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ad48-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad48-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad48-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ad48-120">See also</span></span>

- [<span data-ttu-id="1ad48-121">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1ad48-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="1ad48-122">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1ad48-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="1ad48-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="1ad48-123">Hosting</span></span>](index.md)
