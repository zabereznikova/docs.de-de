---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 9f4b87d6c620a07ee831888086bdab75a689875e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="e83cf-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="e83cf-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="e83cf-103">Registriert einen Cache für die Sitzungstoken mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e83cf-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="e83cf-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="e83cf-104">\<system.identityModel></span></span>  
<span data-ttu-id="e83cf-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e83cf-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e83cf-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="e83cf-106">\<caches></span></span>  
<span data-ttu-id="e83cf-107">\<SessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="e83cf-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e83cf-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e83cf-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e83cf-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e83cf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e83cf-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e83cf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e83cf-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e83cf-111">Attributes</span></span>  
  
|<span data-ttu-id="e83cf-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e83cf-112">Attribute</span></span>|<span data-ttu-id="e83cf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e83cf-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e83cf-114">Typ</span><span class="sxs-lookup"><span data-stu-id="e83cf-114">type</span></span>|<span data-ttu-id="e83cf-115">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e83cf-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e83cf-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e83cf-116">Child Elements</span></span>  
 <span data-ttu-id="e83cf-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="e83cf-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e83cf-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e83cf-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e83cf-119">Element</span><span class="sxs-lookup"><span data-stu-id="e83cf-119">Element</span></span>|<span data-ttu-id="e83cf-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e83cf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e83cf-121">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="e83cf-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="e83cf-122">Registriert die Caches, die von einem Dienst oder eine Auflistung der Security-Tokenhandler verwendet.</span><span class="sxs-lookup"><span data-stu-id="e83cf-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e83cf-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e83cf-123">Example</span></span>  
 <span data-ttu-id="e83cf-124">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Caches für die Aufnahme von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="e83cf-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="e83cf-125">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e83cf-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="e83cf-126">Weitere Informationen zu diesem Beispiel finden Sie unter [WIF Beispiel Codeindex](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="e83cf-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e83cf-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e83cf-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
