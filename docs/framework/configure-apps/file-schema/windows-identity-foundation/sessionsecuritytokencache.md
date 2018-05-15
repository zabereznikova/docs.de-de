---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0b0d3c01a81f110f79f64d75aa2ab2ff2873fedd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="26981-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="26981-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="26981-103">Registriert einen Cache für die Sitzungstoken mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="26981-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="26981-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="26981-104">\<system.identityModel></span></span>  
<span data-ttu-id="26981-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="26981-105">\<identityConfiguration></span></span>  
<span data-ttu-id="26981-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="26981-106">\<caches></span></span>  
<span data-ttu-id="26981-107">\<SessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="26981-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26981-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="26981-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26981-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26981-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26981-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26981-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26981-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="26981-111">Attributes</span></span>  
  
|<span data-ttu-id="26981-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="26981-112">Attribute</span></span>|<span data-ttu-id="26981-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26981-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26981-114">Typ</span><span class="sxs-lookup"><span data-stu-id="26981-114">type</span></span>|<span data-ttu-id="26981-115">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="26981-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26981-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26981-116">Child Elements</span></span>  
 <span data-ttu-id="26981-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="26981-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26981-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26981-118">Parent Elements</span></span>  
  
|<span data-ttu-id="26981-119">Element</span><span class="sxs-lookup"><span data-stu-id="26981-119">Element</span></span>|<span data-ttu-id="26981-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26981-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26981-121">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="26981-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="26981-122">Registriert die Caches, die von einem Dienst oder eine Auflistung der Security-Tokenhandler verwendet.</span><span class="sxs-lookup"><span data-stu-id="26981-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26981-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26981-123">Example</span></span>  
 <span data-ttu-id="26981-124">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Caches für die Aufnahme von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="26981-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="26981-125">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="26981-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="26981-126">Weitere Informationen zu diesem Beispiel finden Sie unter [WIF Beispiel Codeindex](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="26981-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26981-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26981-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
