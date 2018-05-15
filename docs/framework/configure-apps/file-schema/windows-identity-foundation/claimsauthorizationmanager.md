---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 06824e20286f8905ad3a8ac9d2b4a30366a6ec10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="803a7-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="803a7-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="803a7-103">Registriert einen anspruchsautorisierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="803a7-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="803a7-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="803a7-104">\<system.identityModel></span></span>  
<span data-ttu-id="803a7-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="803a7-105">\<identityConfiguration></span></span>  
<span data-ttu-id="803a7-106">\<ClaimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="803a7-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="803a7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="803a7-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="803a7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="803a7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="803a7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="803a7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="803a7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="803a7-110">Attributes</span></span>  
  
|<span data-ttu-id="803a7-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="803a7-111">Attribute</span></span>|<span data-ttu-id="803a7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="803a7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="803a7-113">Typ</span><span class="sxs-lookup"><span data-stu-id="803a7-113">type</span></span>|<span data-ttu-id="803a7-114">Ein benutzerdefinierter Typ, der von abgeleitet ist die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="803a7-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="803a7-115">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="803a7-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="803a7-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="803a7-116">Child Elements</span></span>  
 <span data-ttu-id="803a7-117">Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthorizationManager>` akzeptiert Element untergeordneten Elementen nicht; allerdings von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthorizationManager> können untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="803a7-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="803a7-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="803a7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="803a7-119">Element</span><span class="sxs-lookup"><span data-stu-id="803a7-119">Element</span></span>|<span data-ttu-id="803a7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="803a7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="803a7-121">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="803a7-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="803a7-122">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="803a7-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="803a7-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="803a7-123">Remarks</span></span>  
 <span data-ttu-id="803a7-124">Das Standardverhalten über die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse immer die eingehenden Ansprüche autorisiert.</span><span class="sxs-lookup"><span data-stu-id="803a7-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="803a7-125">Wenn kein `type` -Attribut angegeben ist oder, wenn die `type` Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthorizationManager> -Klasse, die `<claimsAuthorizationManager>` Element akzeptiert keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="803a7-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="803a7-126">Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus der <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="803a7-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="803a7-127">Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthorizationManager>` Element durch Überschreiben der <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="803a7-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="803a7-128">Das Schema definiert die untergeordneten Elemente ist bis zu der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="803a7-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="803a7-129">Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse anspruchsbasierte Zugriffssteuerung in Ihrem Code ab, die identitätskonfiguration bereitstellen, die vom verwiesen wird die `<federationConfiguration>` Element konfiguriert werden, die Ansprüche Autorisierungs-Manager und die Richtlinie, die verwendet wird, um Stellen autorisierungsentscheidungen.</span><span class="sxs-lookup"><span data-stu-id="803a7-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="803a7-130">Dies ist "true" auch in Szenarien, die nicht passiven Web-Szenarien, z. B. Anwendungen für Windows Communication Foundation (WCF) oder eine Anwendung, die nicht webbasierte ist.</span><span class="sxs-lookup"><span data-stu-id="803a7-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="803a7-131">Wenn die Anwendung nicht auf einem passiven Webanwendung ist der `<claimsAuthorizationManager>` -Element (und der untergeordneten Richtlinienelemente, falls vorhanden) sind die einzigen Einstellungen die identitätskonfiguration verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="803a7-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="803a7-132">Alle anderen Einstellungen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="803a7-132">All other settings are ignored.</span></span> <span data-ttu-id="803a7-133">Weitere Informationen finden Sie unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="803a7-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="803a7-134">Diese Element legt die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="803a7-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="803a7-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="803a7-135">Example</span></span>  
 <span data-ttu-id="803a7-136">Das folgende XML zeigt die Konfiguration für die Autorisierung von Ansprüchen-Manager, besteht aus Paaren ressourcenaktion Richtlinie implementiert, von denen jedes booleschen Kombinationen der Ansprüche angibt, die ein anforderer zum Ausführen der Aktion für die Ressource besitzen muss.</span><span class="sxs-lookup"><span data-stu-id="803a7-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="803a7-137">Der Code, der die Ansprüche Autorisierungs-Manager kann mit dieser Richtlinie implementiert finden Sie der `ClaimsBasedAuthorization` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="803a7-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
