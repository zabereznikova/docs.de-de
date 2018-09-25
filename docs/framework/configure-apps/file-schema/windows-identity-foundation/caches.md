---
title: '&lt;Caches&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: a91a389e53354e4f5b26e1510fc2f025300d65cc
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084240"
---
# <a name="ltcachesgt"></a><span data-ttu-id="3fb67-102">&lt;Caches&gt;</span><span class="sxs-lookup"><span data-stu-id="3fb67-102">&lt;caches&gt;</span></span>
<span data-ttu-id="3fb67-103">Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fb67-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="3fb67-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3fb67-104">\<system.identityModel></span></span>  
<span data-ttu-id="3fb67-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3fb67-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3fb67-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="3fb67-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb67-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fb67-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fb67-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3fb67-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3fb67-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3fb67-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fb67-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3fb67-110">Attributes</span></span>  
 <span data-ttu-id="3fb67-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="3fb67-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3fb67-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3fb67-112">Child Elements</span></span>  
  
|<span data-ttu-id="3fb67-113">Element</span><span class="sxs-lookup"><span data-stu-id="3fb67-113">Element</span></span>|<span data-ttu-id="3fb67-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fb67-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fb67-115">\<SessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="3fb67-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="3fb67-116">Registriert ein Zwischenspeicher für Sitzungstoken mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="3fb67-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="3fb67-117">\<TokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="3fb67-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="3fb67-118">Registriert einen tokenwiederholungscache mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="3fb67-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3fb67-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3fb67-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3fb67-120">Element</span><span class="sxs-lookup"><span data-stu-id="3fb67-120">Element</span></span>|<span data-ttu-id="3fb67-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fb67-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fb67-122">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3fb67-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="3fb67-123">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="3fb67-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="3fb67-124">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3fb67-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3fb67-125">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="3fb67-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fb67-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fb67-126">Remarks</span></span>  
 <span data-ttu-id="3fb67-127">Ein `<caches>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="3fb67-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="3fb67-128">Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="3fb67-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="3fb67-129">Die `<caches>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3fb67-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="3fb67-130">Die konfigurierten Caches werden durch dargestellt die <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3fb67-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb67-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fb67-131">Example</span></span>  
 <span data-ttu-id="3fb67-132">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache zum Speichern von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="3fb67-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="3fb67-133">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3fb67-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
