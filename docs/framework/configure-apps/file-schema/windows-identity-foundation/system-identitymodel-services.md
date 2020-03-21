---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152503"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="86962-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="86962-102">\<system.identityModel.services></span></span>
<span data-ttu-id="86962-103">Konfigurationsabschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="86962-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="86962-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86962-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86962-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span><span class="sxs-lookup"><span data-stu-id="86962-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86962-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="86962-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86962-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86962-107">Attributes and Elements</span></span>  
 <span data-ttu-id="86962-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86962-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86962-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="86962-109">Attributes</span></span>  
 <span data-ttu-id="86962-110">Keine</span><span class="sxs-lookup"><span data-stu-id="86962-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86962-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86962-111">Child Elements</span></span>  
  
|<span data-ttu-id="86962-112">Element</span><span class="sxs-lookup"><span data-stu-id="86962-112">Element</span></span>|<span data-ttu-id="86962-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86962-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86962-114">\<FederationConfiguration></span><span class="sxs-lookup"><span data-stu-id="86962-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="86962-115">Enthält die Einstellungen, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> mit denen die <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP-Module (WSFAM) und (SAM) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="86962-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86962-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86962-116">Parent Elements</span></span>  
 <span data-ttu-id="86962-117">Keine</span><span class="sxs-lookup"><span data-stu-id="86962-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86962-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="86962-118">Remarks</span></span>  
 <span data-ttu-id="86962-119">Fügen `<system.identityModel.services>` Sie der Konfigurationsdatei Ihrer Anwendung einen Abschnitt hinzu, um Einstellungen für SAM und WSFAM bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="86962-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="86962-120">Wenn Sie <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die Klasse verwenden, um anspruchsbasierte Zugriffssteuerung in Ihrem Code bereitzustellen, werden der Anspruchsautorisierungs-Manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) und die Richtlinie, die zum Vornehmen von Autorisierungsentscheidungen verwendet wird, über ein `<identityConfiguration>` Element konfiguriert, das implizit oder explizit aus einem `<federationConfiguration>` Element in diesem Abschnitt referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="86962-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="86962-121">Weitere Informationen finden Sie unter **Die Anmerkungen** unter dem [ \<federationConfiguration>-Element.](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="86962-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="86962-122">Der `<system.identityModel.services>` Abschnitt wird <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> durch die Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="86962-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="86962-123">Die Auflistung `<federationConfiguration>` der im Abschnitt konfigurierten untergeordneten Elemente wird durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="86962-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86962-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86962-124">Example</span></span>  
 <span data-ttu-id="86962-125">Der folgende XML-Code `<system.identityModel.services>` zeigt, wie Sie einer Konfigurationsdatei einen Abschnitt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86962-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="86962-126">Sie müssen zunächst Abschnittsdeklarationen sowohl für den `<system.identityModel.services>` Abschnitt als auch für die `<system.identityModel>` Abschnitte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86962-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="86962-127">(Wenn Sie `<system.identityModel.services>` einen Abschnitt hinzufügen, sollten Sie `<system.identityModel>` auch eine Deklaration für den Abschnitt hinzufügen, um sicherzustellen, dass ein Standardabschnitt `<identityConfiguration>` bei Bedarf von der Laufzeit erstellt werden kann.) Nachdem die Abschnittsdeklarationen hinzugefügt wurden, können Sie `<system.identityModel.services>` die Verbundauthentifizierungseinstellungen unter dem Element konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86962-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"
        issuer="http://localhost:15839/wsFederationSTS/Issue"
        realm="http://localhost:50969/" reply="http://localhost:50969/"
        requireHttps="false"
        signOutReply="http://localhost:50969/SignedOutPage.html"
        signOutQueryString="Param1=value2&Param2=value2"
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
