---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 347d1a1cba95bbd4992de95d6617e8828f4fc374
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156900"
---
# \<sessionSecurityTokenCache>

<span data-ttu-id="a1cd1-101">Registriert einen Cache für Sitzungs Token mit einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="a1cd1-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1cd1-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1cd1-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1cd1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a1cd1-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1cd1-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1cd1-105">Attributes</span></span>  
  
|<span data-ttu-id="a1cd1-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a1cd1-106">Attribute</span></span>|<span data-ttu-id="a1cd1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a1cd1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1cd1-108">type</span><span class="sxs-lookup"><span data-stu-id="a1cd1-108">type</span></span>|<span data-ttu-id="a1cd1-109">Ein Typ, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> .</span><span class="sxs-lookup"><span data-stu-id="a1cd1-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1cd1-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1cd1-110">Child Elements</span></span>  

 <span data-ttu-id="a1cd1-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a1cd1-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1cd1-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1cd1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a1cd1-113">Element</span><span class="sxs-lookup"><span data-stu-id="a1cd1-113">Element</span></span>|<span data-ttu-id="a1cd1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1cd1-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="a1cd1-115">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a1cd1-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1cd1-116">Example</span></span>  

 <span data-ttu-id="a1cd1-117">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Speichern von Sitzungs Sicherheits Token ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="a1cd1-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="a1cd1-118">Die Konfiguration wird aus dem `ClaimsAwareWebFarm` Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="a1cd1-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="a1cd1-119">Weitere Informationen zu diesem Beispiel finden Sie unter [Beispiel Index für WIF-Code](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="a1cd1-119">For more information about this sample, see [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1cd1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1cd1-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
