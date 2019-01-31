---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 59d47eda97e97629408ece12a1d1dfbe804feb3e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268094"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="b7d84-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="b7d84-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="b7d84-102">Registriert einen anspruchsautorisierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="b7d84-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="b7d84-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b7d84-103">\<system.identityModel></span></span>  
<span data-ttu-id="b7d84-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b7d84-104">\<identityConfiguration></span></span>  
<span data-ttu-id="b7d84-105">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="b7d84-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d84-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7d84-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7d84-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b7d84-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b7d84-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7d84-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7d84-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7d84-109">Attributes</span></span>  
  
|<span data-ttu-id="b7d84-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="b7d84-110">Attribute</span></span>|<span data-ttu-id="b7d84-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7d84-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7d84-112">Typ</span><span class="sxs-lookup"><span data-stu-id="b7d84-112">type</span></span>|<span data-ttu-id="b7d84-113">Einen benutzerdefinierten Typ abgeleitet, die die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b7d84-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="b7d84-114">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="b7d84-114">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7d84-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7d84-115">Child Elements</span></span>  
 <span data-ttu-id="b7d84-116">Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthorizationManager>` Element nimmt keine untergeordneten Elemente, aber von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthorizationManager> können untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="b7d84-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7d84-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7d84-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b7d84-118">Element</span><span class="sxs-lookup"><span data-stu-id="b7d84-118">Element</span></span>|<span data-ttu-id="b7d84-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7d84-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7d84-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b7d84-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="b7d84-121">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="b7d84-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d84-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7d84-122">Remarks</span></span>  
 <span data-ttu-id="b7d84-123">Das Standardverhalten durch die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse immer autorisiert die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="b7d84-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="b7d84-124">Wenn kein `type` -Attribut angegeben ist oder wenn die `type` -Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthorizationManager> -Klasse, die `<claimsAuthorizationManager>` Element nimmt keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="b7d84-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="b7d84-125">Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus den <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b7d84-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="b7d84-126">Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthorizationManager>` Element durch das Überschreiben der <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b7d84-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="b7d84-127">Das Schema für die untergeordneten Elemente definiert ist, bis zu den Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b7d84-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7d84-128">Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code die identitätskonfiguration bereitzustellen, auf die verweist, die `<federationConfiguration>` -Element konfiguriert die anspruchsautorisierungs-Manager und die Richtlinie, die verwendet wird, um sicherzustellen autorisierungsentscheidungen.</span><span class="sxs-lookup"><span data-stu-id="b7d84-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="b7d84-129">Dies gilt, auch in Szenarien, die nicht passiven Webszenarien, z. B. Anwendungen für Windows Communication Foundation (WCF) oder eine Anwendung, die nicht webbasierte ist.</span><span class="sxs-lookup"><span data-stu-id="b7d84-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="b7d84-130">Wenn die Anwendung nicht mit einer passiven Webanwendung ist die `<claimsAuthorizationManager>` -Element (und seine untergeordneten Richtlinienelemente, sofern vorhanden) der identitätskonfiguration verwiesen wird die einzigen Einstellungen, die angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7d84-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="b7d84-131">Alle anderen Einstellungen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b7d84-131">All other settings are ignored.</span></span> <span data-ttu-id="b7d84-132">Weitere Informationen finden Sie unter den [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="b7d84-132">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="b7d84-133">Dieses Element legt die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b7d84-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7d84-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7d84-134">Example</span></span>  
 <span data-ttu-id="b7d84-135">Das folgende XML zeigt die Konfiguration für eine Autorisierung von Ansprüchen-Manager, bestehend aus Ressourcen-Aktionspaare Richtlinie implementiert, von denen jede boolesche Kombinationen von Ansprüchen angibt, die ein anforderer zum Ausführen der Aktion für die Ressource besitzen muss.</span><span class="sxs-lookup"><span data-stu-id="b7d84-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="b7d84-136">Der Code, den anspruchsautorisierungs-Manager verwenden Sie diese Richtlinie implementiert, finden Sie der `ClaimsBasedAuthorization` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b7d84-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
