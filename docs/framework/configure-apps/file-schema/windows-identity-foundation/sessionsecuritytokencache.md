---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943713"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="294a4-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="294a4-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="294a4-102">Registriert einen Cache für Sitzungs Token mit einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="294a4-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="294a4-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="294a4-103">\<system.identityModel></span></span>  
<span data-ttu-id="294a4-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="294a4-104">\<identityConfiguration></span></span>  
<span data-ttu-id="294a4-105">\<Caches ></span><span class="sxs-lookup"><span data-stu-id="294a4-105">\<caches></span></span>  
<span data-ttu-id="294a4-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="294a4-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="294a4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="294a4-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="294a4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="294a4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="294a4-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="294a4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="294a4-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="294a4-110">Attributes</span></span>  
  
|<span data-ttu-id="294a4-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="294a4-111">Attribute</span></span>|<span data-ttu-id="294a4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="294a4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="294a4-113">Typ</span><span class="sxs-lookup"><span data-stu-id="294a4-113">type</span></span>|<span data-ttu-id="294a4-114">Ein Typ, der von der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="294a4-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="294a4-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="294a4-115">Child Elements</span></span>  
 <span data-ttu-id="294a4-116">None</span><span class="sxs-lookup"><span data-stu-id="294a4-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="294a4-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="294a4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="294a4-118">Element</span><span class="sxs-lookup"><span data-stu-id="294a4-118">Element</span></span>|<span data-ttu-id="294a4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="294a4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="294a4-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="294a4-120">\<caches></span></span>](caches.md)|<span data-ttu-id="294a4-121">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="294a4-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="294a4-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="294a4-122">Example</span></span>  
 <span data-ttu-id="294a4-123">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungs<xref:System.IdentityModel.Tokens.SessionSecurityToken>Sicherheits Token ().</span><span class="sxs-lookup"><span data-stu-id="294a4-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="294a4-124">Die Konfiguration wird aus dem `ClaimsAwareWebFarm` Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="294a4-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="294a4-125">Weitere Informationen zu diesem Beispiel finden Sie unter [Beispiel Index für WIF-Code](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="294a4-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="294a4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="294a4-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
