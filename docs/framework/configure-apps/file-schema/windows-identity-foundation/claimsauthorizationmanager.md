---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 0718f789ff4d99fb4e2651a9a704da4248cd5f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158434"
---
# \<claimsAuthorizationManager>

<span data-ttu-id="1e0e8-101">Registriert einen Anspruchs Autorisierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-101">Registers a claims authorization manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="1e0e8-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e0e8-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e0e8-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1e0e8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1e0e8-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e0e8-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e0e8-105">Attributes</span></span>  
  
|<span data-ttu-id="1e0e8-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1e0e8-106">Attribute</span></span>|<span data-ttu-id="1e0e8-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e0e8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e0e8-108">type</span><span class="sxs-lookup"><span data-stu-id="1e0e8-108">type</span></span>|<span data-ttu-id="1e0e8-109">Ein benutzerdefinierter Typ, der von der-Klasse abgeleitet wird <xref:System.Security.Claims.ClaimsAuthorizationManager> .</span><span class="sxs-lookup"><span data-stu-id="1e0e8-109">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="1e0e8-110">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e8-110">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e0e8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e0e8-111">Child Elements</span></span>  

 <span data-ttu-id="1e0e8-112">Wenn kein-Attribut vorhanden ist `type` , oder wenn das- `type` Attribut auf die- <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse verweist, nimmt das- `<claimsAuthorizationManager>` Element keine untergeordneten Elemente an. von abgeleitete Klassen können jedoch untergeordnete <xref:System.Security.Claims.ClaimsAuthorizationManager> Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e0e8-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e0e8-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1e0e8-114">Element</span><span class="sxs-lookup"><span data-stu-id="1e0e8-114">Element</span></span>|<span data-ttu-id="1e0e8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e0e8-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="1e0e8-116">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e0e8-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1e0e8-117">Remarks</span></span>  

 <span data-ttu-id="1e0e8-118">Das Standardverhalten, das durch die-Klasse bereitgestellt wird, <xref:System.Security.Claims.ClaimsAuthorizationManager> autorisiert immer eingehende Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="1e0e8-119">Wenn kein- `type` Attribut angegeben wird oder wenn das- `type` Attribut die- <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse angibt, nimmt das- `<claimsAuthorizationManager>` Element keine untergeordneten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="1e0e8-120">Sie können das `type` Attribut angeben, um einen von der-Klasse abgeleiteten Typ <xref:System.Security.Claims.ClaimsAuthorizationManager> zu registrieren, um benutzerdefiniertes Verhalten zu implementieren</span><span class="sxs-lookup"><span data-stu-id="1e0e8-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="1e0e8-121">Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente des-Elements unterstützen `<claimsAuthorizationManager>` , indem Sie die- <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> Methode zum Verarbeiten dieser Elemente überschreiben.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-121">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="1e0e8-122">Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1e0e8-123">Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -oder die-Klasse verwenden, <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> um eine Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen, konfiguriert die Identitäts Konfiguration, auf die das-Element verweist, `<federationConfiguration>` den anspruchsautorisierungs-Manager und die Richtlinie, die für Autorisierungs Entscheidungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-123">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="1e0e8-124">Dies gilt auch für Szenarien, bei denen es sich nicht um passive Webszenarien handelt, z. b. Windows Communication Foundation (WCF)-Anwendungen oder eine nicht webbasierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-124">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="1e0e8-125">Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, `<claimsAuthorizationManager>` werden das-Element (und seine untergeordneten Richtlinien Elemente, falls vorhanden) der Identitäts Konfiguration, auf die verwiesen wird, als einzige Einstellung angewendet.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-125">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="1e0e8-126">Alle anderen Einstellungen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-126">All other settings are ignored.</span></span> <span data-ttu-id="1e0e8-127">Weitere Informationen finden Sie unter dem- [\<federationConfiguration>](federationconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-127">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="1e0e8-128">Mit diesem Element wird die-Eigenschaft festgelegt <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1e0e8-128">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e0e8-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e0e8-129">Example</span></span>  

 <span data-ttu-id="1e0e8-130">Der folgende XML-Code zeigt die Konfiguration für einen anspruchsautorisierungs-Manager, der eine Richtlinie implementiert, die aus Ressourcen Aktions Paaren besteht, von denen jede boolesche Kombinationen der Ansprüche angibt, die ein Anforderer besitzen muss, um die Aktion für die Ressource auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-130">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="1e0e8-131">Der Code, der den Anspruchs Autorisierungs-Manager implementiert, der diese Richtlinie verwenden kann, finden Sie im `ClaimsBasedAuthorization` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="1e0e8-131">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
