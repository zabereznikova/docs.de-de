---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252163"
---
# <a name="caches"></a><span data-ttu-id="cd4d0-101">\<Caches ></span><span class="sxs-lookup"><span data-stu-id="cd4d0-101">\<caches></span></span>
<span data-ttu-id="cd4d0-102">Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="cd4d0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cd4d0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cd4d0-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cd4d0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cd4d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cd4d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cd4d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Caches >**</span><span class="sxs-lookup"><span data-stu-id="cd4d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4d0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd4d0-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd4d0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd4d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd4d0-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd4d0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd4d0-110">Attributes</span></span>  
 <span data-ttu-id="cd4d0-111">None</span><span class="sxs-lookup"><span data-stu-id="cd4d0-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd4d0-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd4d0-112">Child Elements</span></span>  
  
|<span data-ttu-id="cd4d0-113">Element</span><span class="sxs-lookup"><span data-stu-id="cd4d0-113">Element</span></span>|<span data-ttu-id="cd4d0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd4d0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd4d0-115">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="cd4d0-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="cd4d0-116">Registriert einen Cache für Sitzungs Token mit einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="cd4d0-117">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="cd4d0-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="cd4d0-118">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd4d0-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd4d0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cd4d0-120">Element</span><span class="sxs-lookup"><span data-stu-id="cd4d0-120">Element</span></span>|<span data-ttu-id="cd4d0-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd4d0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd4d0-122">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cd4d0-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="cd4d0-123">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="cd4d0-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cd4d0-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="cd4d0-125">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd4d0-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd4d0-126">Remarks</span></span>  
 <span data-ttu-id="cd4d0-127">Ein `<caches>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="cd4d0-128">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="cd4d0-129">Das `<caches>` -Element wird durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="cd4d0-130">Die konfigurierten Caches werden durch die <xref:System.IdentityModel.Configuration.IdentityModelCaches> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4d0-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd4d0-131">Example</span></span>  
 <span data-ttu-id="cd4d0-132">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungs<xref:System.IdentityModel.Tokens.SessionSecurityToken>Sicherheits Token ().</span><span class="sxs-lookup"><span data-stu-id="cd4d0-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="cd4d0-133">Die Konfiguration wird aus dem `ClaimsAwareWebFarm` Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="cd4d0-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
