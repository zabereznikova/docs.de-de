---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252163"
---
# \<caches>
<span data-ttu-id="61d8b-101">Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61d8b-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="61d8b-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="61d8b-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61d8b-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61d8b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="61d8b-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61d8b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61d8b-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="61d8b-105">Attributes</span></span>  
 <span data-ttu-id="61d8b-106">Keine</span><span class="sxs-lookup"><span data-stu-id="61d8b-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61d8b-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61d8b-107">Child Elements</span></span>  
  
|<span data-ttu-id="61d8b-108">Element</span><span class="sxs-lookup"><span data-stu-id="61d8b-108">Element</span></span>|<span data-ttu-id="61d8b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61d8b-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="61d8b-110">Registriert einen Cache für Sitzungs Token mit einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="61d8b-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="61d8b-111">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="61d8b-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61d8b-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61d8b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="61d8b-113">Element</span><span class="sxs-lookup"><span data-stu-id="61d8b-113">Element</span></span>|<span data-ttu-id="61d8b-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61d8b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="61d8b-115">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="61d8b-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="61d8b-116">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="61d8b-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61d8b-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="61d8b-117">Remarks</span></span>  
 <span data-ttu-id="61d8b-118">Ein- `<caches>` Element kann auf der Dienst Ebene unterhalb des- `<identityConfiguration>` Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem-Element angegeben werden `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="61d8b-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="61d8b-119">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="61d8b-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="61d8b-120">Das- `<caches>` Element wird durch die- <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="61d8b-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="61d8b-121">Die konfigurierten Caches werden durch die- <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="61d8b-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61d8b-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61d8b-122">Example</span></span>  
 <span data-ttu-id="61d8b-123">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungs Sicherheits Token ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="61d8b-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="61d8b-124">Die Konfiguration wird aus dem `ClaimsAwareWebFarm` Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="61d8b-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
