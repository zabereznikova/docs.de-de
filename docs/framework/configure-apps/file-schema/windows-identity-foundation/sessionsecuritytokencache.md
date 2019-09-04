---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251831"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="c82b3-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="c82b3-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="c82b3-102">Registriert einen Cache für Sitzungs Token mit einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="c82b3-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="c82b3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c82b3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c82b3-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c82b3-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c82b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c82b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c82b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Caches >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="c82b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="c82b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessionsecuritytokencache->**</span><span class="sxs-lookup"><span data-stu-id="c82b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c82b3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c82b3-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c82b3-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c82b3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c82b3-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c82b3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c82b3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c82b3-111">Attributes</span></span>  
  
|<span data-ttu-id="c82b3-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c82b3-112">Attribute</span></span>|<span data-ttu-id="c82b3-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c82b3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c82b3-114">Typ</span><span class="sxs-lookup"><span data-stu-id="c82b3-114">type</span></span>|<span data-ttu-id="c82b3-115">Ein Typ, der von der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c82b3-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c82b3-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c82b3-116">Child Elements</span></span>  
 <span data-ttu-id="c82b3-117">None</span><span class="sxs-lookup"><span data-stu-id="c82b3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c82b3-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c82b3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c82b3-119">Element</span><span class="sxs-lookup"><span data-stu-id="c82b3-119">Element</span></span>|<span data-ttu-id="c82b3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c82b3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c82b3-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="c82b3-121">\<caches></span></span>](caches.md)|<span data-ttu-id="c82b3-122">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="c82b3-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c82b3-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c82b3-123">Example</span></span>  
 <span data-ttu-id="c82b3-124">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungs<xref:System.IdentityModel.Tokens.SessionSecurityToken>Sicherheits Token ().</span><span class="sxs-lookup"><span data-stu-id="c82b3-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="c82b3-125">Die Konfiguration wird aus dem `ClaimsAwareWebFarm` Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="c82b3-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="c82b3-126">Weitere Informationen zu diesem Beispiel finden Sie unter [Beispiel Index für WIF-Code](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="c82b3-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c82b3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c82b3-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
