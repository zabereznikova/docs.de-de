---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e909756a58d5008d917fca84af0e478fc4878d2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156809"
---
# \<system.identityModel.services>

<span data-ttu-id="e676f-102">Konfigurations Abschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e676f-102">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
## <a name="syntax"></a><span data-ttu-id="e676f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="e676f-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e676f-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e676f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e676f-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e676f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e676f-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="e676f-106">Attributes</span></span>  

 <span data-ttu-id="e676f-107">Keine</span><span class="sxs-lookup"><span data-stu-id="e676f-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e676f-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e676f-108">Child Elements</span></span>  
  
|<span data-ttu-id="e676f-109">Element</span><span class="sxs-lookup"><span data-stu-id="e676f-109">Element</span></span>|<span data-ttu-id="e676f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e676f-110">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="e676f-111">Enthält die Einstellungen, die die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> HTTP-Module (wsfam) und <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e676f-111">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e676f-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e676f-112">Parent Elements</span></span>  

 <span data-ttu-id="e676f-113">Keine</span><span class="sxs-lookup"><span data-stu-id="e676f-113">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e676f-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e676f-114">Remarks</span></span>  

 <span data-ttu-id="e676f-115">Fügen Sie der `<system.identityModel.services>` Konfigurationsdatei Ihrer Anwendung einen Abschnitt hinzu, um die Einstellungen für Sam und wsfam bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e676f-115">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e676f-116">Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -Klasse oder die-Klasse verwenden, <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> um eine Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen, werden der anspruchsautorisierungs-Manager ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) und die Richtlinie, die zum Treffen von Autorisierungs Entscheidungen verwendet werden, über ein Element konfiguriert, `<identityConfiguration>` das implizit oder explizit von einem- `<federationConfiguration>` Element in diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e676f-116">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="e676f-117">Weitere Informationen finden **Sie in den Hinweisen unter dem-** [\<federationConfiguration>](federationconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e676f-117">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="e676f-118">Der- `<system.identityModel.services>` Abschnitt wird durch die- <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e676f-118">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="e676f-119">Die Auflistung der untergeordneten Elemente, die `<federationConfiguration>` im-Abschnitt konfiguriert wurden, wird durch die- <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e676f-119">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e676f-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e676f-120">Example</span></span>  

 <span data-ttu-id="e676f-121">Der folgende XML-Code zeigt, wie Sie einer Konfigurationsdatei einen-Abschnitt hinzufügen `<system.identityModel.services>` .</span><span class="sxs-lookup"><span data-stu-id="e676f-121">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="e676f-122">Sie müssen zunächst Abschnitts Deklarationen für den `<system.identityModel.services>` Abschnitt und die Abschnitte hinzufügen `<system.identityModel>` .</span><span class="sxs-lookup"><span data-stu-id="e676f-122">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="e676f-123">(Wenn Sie einen Abschnitt hinzufügen `<system.identityModel.services>` , sollten Sie auch eine Deklaration für den Abschnitt hinzufügen, `<system.identityModel>` um sicherzustellen, dass `<identityConfiguration>` ggf. ein Standardabschnitt von der Laufzeit erstellt werden kann.) Nachdem die Abschnitts Deklarationen hinzugefügt wurden, können Sie die Einstellungen für die Verbund Authentifizierung unter dem- `<system.identityModel.services>` Element konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e676f-123">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
