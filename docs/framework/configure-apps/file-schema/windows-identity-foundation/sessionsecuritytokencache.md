---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: b812673ac1c015adde357d3c0707d85643aad3e9
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084331"
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="aa132-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="aa132-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="aa132-103">Registriert ein Zwischenspeicher für Sitzungstoken mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="aa132-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="aa132-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="aa132-104">\<system.identityModel></span></span>  
<span data-ttu-id="aa132-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="aa132-105">\<identityConfiguration></span></span>  
<span data-ttu-id="aa132-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="aa132-106">\<caches></span></span>  
<span data-ttu-id="aa132-107">\<SessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="aa132-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa132-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa132-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa132-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa132-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aa132-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa132-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa132-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa132-111">Attributes</span></span>  
  
|<span data-ttu-id="aa132-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="aa132-112">Attribute</span></span>|<span data-ttu-id="aa132-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa132-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa132-114">Typ</span><span class="sxs-lookup"><span data-stu-id="aa132-114">type</span></span>|<span data-ttu-id="aa132-115">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="aa132-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa132-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa132-116">Child Elements</span></span>  
 <span data-ttu-id="aa132-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="aa132-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa132-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa132-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aa132-119">Element</span><span class="sxs-lookup"><span data-stu-id="aa132-119">Element</span></span>|<span data-ttu-id="aa132-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa132-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa132-121">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="aa132-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="aa132-122">Registriert die Caches, die von einem Dienst oder ein Sicherheitstoken-Handlerauflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa132-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aa132-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa132-123">Example</span></span>  
 <span data-ttu-id="aa132-124">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache zum Speichern von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="aa132-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="aa132-125">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="aa132-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="aa132-126">Weitere Informationen zu diesem Beispiel finden Sie unter [Index für WIF-Codebeispiele](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="aa132-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa132-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa132-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
