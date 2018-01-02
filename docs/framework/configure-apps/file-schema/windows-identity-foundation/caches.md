---
title: '&lt;Caches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b9dfa7b2f0952f3f9e224ad51fd4d9c0c263ce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcachesgt"></a><span data-ttu-id="acd89-102">&lt;Caches&gt;</span><span class="sxs-lookup"><span data-stu-id="acd89-102">&lt;caches&gt;</span></span>
<span data-ttu-id="acd89-103">Registriert die Caches für die Sitzungstoken und token-Replay-Erkennung verwendet.</span><span class="sxs-lookup"><span data-stu-id="acd89-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="acd89-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="acd89-104">\<system.identityModel></span></span>  
<span data-ttu-id="acd89-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="acd89-105">\<identityConfiguration></span></span>  
<span data-ttu-id="acd89-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="acd89-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd89-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="acd89-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acd89-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="acd89-108">Attributes and Elements</span></span>  
 <span data-ttu-id="acd89-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="acd89-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acd89-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="acd89-110">Attributes</span></span>  
 <span data-ttu-id="acd89-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="acd89-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="acd89-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acd89-112">Child Elements</span></span>  
  
|<span data-ttu-id="acd89-113">Element</span><span class="sxs-lookup"><span data-stu-id="acd89-113">Element</span></span>|<span data-ttu-id="acd89-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acd89-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acd89-115">\<SessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="acd89-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="acd89-116">Registriert einen Cache für die Sitzungstoken mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="acd89-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="acd89-117">\<TokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="acd89-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="acd89-118">Registriert einen token-Replay-Cache mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="acd89-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acd89-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acd89-119">Parent Elements</span></span>  
  
|<span data-ttu-id="acd89-120">Element</span><span class="sxs-lookup"><span data-stu-id="acd89-120">Element</span></span>|<span data-ttu-id="acd89-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acd89-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acd89-122">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="acd89-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="acd89-123">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="acd89-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="acd89-124">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="acd89-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="acd89-125">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="acd89-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acd89-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acd89-126">Remarks</span></span>  
 <span data-ttu-id="acd89-127">Ein `<caches>` Element angegeben werden kann, auf Dienstebene unter der `<identityConfiguration>` Element oder auf die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="acd89-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="acd89-128">Einstellungen für eine Sammlung Tokenhandler außer Kraft für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="acd89-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="acd89-129">Die `<caches>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="acd89-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="acd89-130">Die konfigurierten Caches werden durch dargestellt die <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse.</span><span class="sxs-lookup"><span data-stu-id="acd89-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acd89-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acd89-131">Example</span></span>  
 <span data-ttu-id="acd89-132">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Caches für die Aufnahme von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="acd89-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="acd89-133">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="acd89-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
