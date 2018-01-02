---
title: '&lt;system.identityModel.services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 03c2fa7fe65650b760937ef06b848152893e023b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemidentitymodelservicesgt"></a><span data-ttu-id="a6bcd-102">&lt;system.identityModel.services&gt;</span><span class="sxs-lookup"><span data-stu-id="a6bcd-102">&lt;system.identityModel.services&gt;</span></span>
<span data-ttu-id="a6bcd-103">Der Konfigurationsabschnitt für die Authentifizierung mit dem WS-Verbund-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="a6bcd-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="a6bcd-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6bcd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6bcd-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6bcd-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a6bcd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a6bcd-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6bcd-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a6bcd-108">Attributes</span></span>  
 <span data-ttu-id="a6bcd-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="a6bcd-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6bcd-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6bcd-110">Child Elements</span></span>  
  
|<span data-ttu-id="a6bcd-111">Element</span><span class="sxs-lookup"><span data-stu-id="a6bcd-111">Element</span></span>|<span data-ttu-id="a6bcd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6bcd-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6bcd-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="a6bcd-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="a6bcd-114">Enthält die Einstellungen zur Konfiguration der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP-Module.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6bcd-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6bcd-115">Parent Elements</span></span>  
 <span data-ttu-id="a6bcd-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="a6bcd-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6bcd-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6bcd-117">Remarks</span></span>  
 <span data-ttu-id="a6bcd-118">Hinzufügen einer `<system.identityModel.services>` Abschnitt aus, um Sie in der Konfigurationsdatei Ihrer Anwendung das SAM und WSFAM Einstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6bcd-119">Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> -Klasse, anspruchsbasierte Zugriffssteuerung in Ihrem Code, den Ansprüche Autorisierungs-Manager bereitzustellen (<xref:System.Security.Claims.ClaimsAuthorizationManager>) und die Richtlinie, die verwendet wird, um autorisierungsentscheidungen zu treffen sind so konfiguriert, über ein `<identityConfiguration>` Element, das implizit oder explizit verwiesen wird, aus einer `<federationConfiguration>` Element in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="a6bcd-120">Weitere Informationen finden Sie unter der **"Hinweise"** unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="a6bcd-121">Die `<system.identityModel.services>` Abschnitt wird dargestellt, indem die <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="a6bcd-122">Die Auflistung untergeordneter `<federationConfiguration>` Elemente, die den im Abschnitt konfigurierten wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6bcd-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6bcd-123">Example</span></span>  
 <span data-ttu-id="a6bcd-124">Das folgende XML zeigt das Hinzufügen einer `<system.identityModel.services>` Abschnitt aus, um eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="a6bcd-125">Sie müssen zunächst Abschnitt Deklarationen für beide Hinzufügen der `<system.identityModel.services>` Abschnitt und der `<system.identityModel>` Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="a6bcd-126">(Beim Hinzufügen einer `<system.identityModel.services>` Abschnitt, sollten Sie auch eine Deklaration für Hinzufügen der `<system.identityModel>` Abschnitt aus, um sicherzustellen, dass auf den Standardwert `<identityConfiguration>` Abschnitt bei Bedarf von der Laufzeit erstellt werden.) Nachdem die Abschnitt Deklarationen hinzugefügt wurden, können Sie konfigurieren, dass Verbundauthentifizierung Einstellungen unter dem `<system.identityModel.services>` Element.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
