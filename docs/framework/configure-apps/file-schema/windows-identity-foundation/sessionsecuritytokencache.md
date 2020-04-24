---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646066"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="4751b-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="4751b-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="4751b-102">Registriert einen Cache für Sitzungstoken mit einem Dienst oder einer Sicherheitstokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="4751b-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="4751b-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4751b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4751b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4751b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4751b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4751b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4751b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Caches>**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="4751b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="4751b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span><span class="sxs-lookup"><span data-stu-id="4751b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4751b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4751b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4751b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4751b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4751b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4751b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4751b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4751b-111">Attributes</span></span>  
  
|<span data-ttu-id="4751b-112">attribute</span><span class="sxs-lookup"><span data-stu-id="4751b-112">Attribute</span></span>|<span data-ttu-id="4751b-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4751b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4751b-114">type</span><span class="sxs-lookup"><span data-stu-id="4751b-114">type</span></span>|<span data-ttu-id="4751b-115">Ein Typ, der von <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> der Klasse ableitet.</span><span class="sxs-lookup"><span data-stu-id="4751b-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4751b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4751b-116">Child Elements</span></span>  
 <span data-ttu-id="4751b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="4751b-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4751b-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4751b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4751b-119">Element</span><span class="sxs-lookup"><span data-stu-id="4751b-119">Element</span></span>|<span data-ttu-id="4751b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4751b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4751b-121">\<Caches></span><span class="sxs-lookup"><span data-stu-id="4751b-121">\<caches></span></span>](caches.md)|<span data-ttu-id="4751b-122">Registriert die Caches, die von einem Dienst oder einer Sicherheitstokenhandlersammlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4751b-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4751b-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4751b-123">Example</span></span>  
 <span data-ttu-id="4751b-124">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungssicherheitstoken (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="4751b-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="4751b-125">Die Konfiguration wird `ClaimsAwareWebFarm` aus dem Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="4751b-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="4751b-126">Weitere Informationen zu diesem Beispiel finden Sie unter [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="4751b-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4751b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4751b-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
