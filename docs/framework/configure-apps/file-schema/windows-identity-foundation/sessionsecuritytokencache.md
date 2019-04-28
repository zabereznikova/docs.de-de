---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793795"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="d3a85-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d3a85-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="d3a85-102">Registriert ein Zwischenspeicher für Sitzungstoken mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="d3a85-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="d3a85-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d3a85-103">\<system.identityModel></span></span>  
<span data-ttu-id="d3a85-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d3a85-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d3a85-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="d3a85-105">\<caches></span></span>  
<span data-ttu-id="d3a85-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d3a85-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a85-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3a85-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3a85-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3a85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d3a85-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3a85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3a85-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3a85-110">Attributes</span></span>  
  
|<span data-ttu-id="d3a85-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d3a85-111">Attribute</span></span>|<span data-ttu-id="d3a85-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3a85-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3a85-113">Typ</span><span class="sxs-lookup"><span data-stu-id="d3a85-113">type</span></span>|<span data-ttu-id="d3a85-114">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d3a85-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3a85-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3a85-115">Child Elements</span></span>  
 <span data-ttu-id="d3a85-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="d3a85-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3a85-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3a85-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d3a85-118">Element</span><span class="sxs-lookup"><span data-stu-id="d3a85-118">Element</span></span>|<span data-ttu-id="d3a85-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3a85-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3a85-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="d3a85-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="d3a85-121">Registriert die Caches, die von einem Dienst oder ein Sicherheitstoken-Handlerauflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3a85-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3a85-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3a85-122">Example</span></span>  
 <span data-ttu-id="d3a85-123">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache zum Speichern von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="d3a85-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d3a85-124">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d3a85-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="d3a85-125">Weitere Informationen zu diesem Beispiel finden Sie unter [Index für WIF-Codebeispiele](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="d3a85-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3a85-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3a85-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
