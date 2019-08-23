---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941963"
---
# <a name="caches"></a><span data-ttu-id="02d6a-101">\<Caches ></span><span class="sxs-lookup"><span data-stu-id="02d6a-101">\<caches></span></span>
<span data-ttu-id="02d6a-102">Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02d6a-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="02d6a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="02d6a-103">\<system.identityModel></span></span>  
<span data-ttu-id="02d6a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="02d6a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="02d6a-105">\<Caches ></span><span class="sxs-lookup"><span data-stu-id="02d6a-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d6a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="02d6a-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02d6a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02d6a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="02d6a-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02d6a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02d6a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="02d6a-109">Attributes</span></span>  
 <span data-ttu-id="02d6a-110">None</span><span class="sxs-lookup"><span data-stu-id="02d6a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02d6a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02d6a-111">Child Elements</span></span>  
  
|<span data-ttu-id="02d6a-112">Element</span><span class="sxs-lookup"><span data-stu-id="02d6a-112">Element</span></span>|<span data-ttu-id="02d6a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02d6a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02d6a-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="02d6a-114">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="02d6a-115">Registriert einen Cache für Sitzungs Token mit einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="02d6a-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="02d6a-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="02d6a-116">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="02d6a-117">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="02d6a-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02d6a-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02d6a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="02d6a-119">Element</span><span class="sxs-lookup"><span data-stu-id="02d6a-119">Element</span></span>|<span data-ttu-id="02d6a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02d6a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02d6a-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="02d6a-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="02d6a-122">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="02d6a-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="02d6a-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="02d6a-123">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="02d6a-124">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="02d6a-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d6a-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02d6a-125">Remarks</span></span>  
 <span data-ttu-id="02d6a-126">Ein `<caches>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02d6a-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="02d6a-127">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="02d6a-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="02d6a-128">Das `<caches>` -Element wird durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="02d6a-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="02d6a-129">Die konfigurierten Caches werden durch die <xref:System.IdentityModel.Configuration.IdentityModelCaches> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="02d6a-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d6a-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02d6a-130">Example</span></span>  
 <span data-ttu-id="02d6a-131">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungs<xref:System.IdentityModel.Tokens.SessionSecurityToken>Sicherheits Token ().</span><span class="sxs-lookup"><span data-stu-id="02d6a-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="02d6a-132">Die Konfiguration wird aus dem `ClaimsAwareWebFarm` Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="02d6a-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
