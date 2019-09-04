---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251813"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="53fa9-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="53fa9-102">\<system.identityModel.services></span></span>
<span data-ttu-id="53fa9-103">Konfigurations Abschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="53fa9-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="53fa9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53fa9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53fa9-105">&nbsp;&nbsp; **\<System. IdentityModel. Services->**</span><span class="sxs-lookup"><span data-stu-id="53fa9-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53fa9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="53fa9-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53fa9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53fa9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="53fa9-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53fa9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53fa9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="53fa9-109">Attributes</span></span>  
 <span data-ttu-id="53fa9-110">None</span><span class="sxs-lookup"><span data-stu-id="53fa9-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53fa9-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53fa9-111">Child Elements</span></span>  
  
|<span data-ttu-id="53fa9-112">Element</span><span class="sxs-lookup"><span data-stu-id="53fa9-112">Element</span></span>|<span data-ttu-id="53fa9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53fa9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53fa9-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="53fa9-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="53fa9-115">Enthält die Einstellungen, die die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> http <xref:System.IdentityModel.Services.SessionAuthenticationModule> -Module (wsfam) und (Sam) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="53fa9-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53fa9-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53fa9-116">Parent Elements</span></span>  
 <span data-ttu-id="53fa9-117">None</span><span class="sxs-lookup"><span data-stu-id="53fa9-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53fa9-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53fa9-118">Remarks</span></span>  
 <span data-ttu-id="53fa9-119">Fügen Sie `<system.identityModel.services>` der Konfigurationsdatei Ihrer Anwendung einen Abschnitt hinzu, um die Einstellungen für Sam und wsfam bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="53fa9-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="53fa9-120">Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -Klasse <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die-Klasse verwenden, um eine `<identityConfiguration>` Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen<xref:System.Security.Claims.ClaimsAuthorizationManager>, werden der anspruchsautorisierungs-Manager () und die Richtlinie, die für Autorisierungs Entscheidungen verwendet wird, über Element, das implizit oder explizit von einem `<federationConfiguration>` -Element in diesem Abschnitt referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="53fa9-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="53fa9-121">Weitere Informationen finden **Sie in den** Hinweisen unter dem [ \<Element federationconfiguration >](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="53fa9-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="53fa9-122">Der `<system.identityModel.services>` -Abschnitt wird durch die <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="53fa9-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="53fa9-123">Die Auflistung der `<federationConfiguration>` untergeordneten Elemente, die im-Abschnitt konfiguriert wurden <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> , wird durch die-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="53fa9-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53fa9-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53fa9-124">Example</span></span>  
 <span data-ttu-id="53fa9-125">Der folgende XML-Code zeigt, wie `<system.identityModel.services>` Sie einer Konfigurationsdatei einen-Abschnitt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53fa9-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="53fa9-126">Sie müssen zunächst Abschnitts Deklarationen für den `<system.identityModel.services>` Abschnitt und die `<system.identityModel>` Abschnitte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53fa9-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="53fa9-127">(Wenn Sie einen `<system.identityModel.services>` Abschnitt hinzufügen, sollten Sie auch eine Deklaration für den `<system.identityModel>` Abschnitt hinzufügen, um `<identityConfiguration>` sicherzustellen, dass ggf. ein Standardabschnitt von der Laufzeit erstellt werden kann.) Nachdem die Abschnitts Deklarationen hinzugefügt wurden, können Sie die Einstellungen für die Verbund Authentifizierung `<system.identityModel.services>` unter dem-Element konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="53fa9-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
