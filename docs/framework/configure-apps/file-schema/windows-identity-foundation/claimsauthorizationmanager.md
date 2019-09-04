---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ddbe8a862940272e4192a3f4c0abdc1f9e8b5d48
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252082"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="2c32e-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="2c32e-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="2c32e-102">Registriert einen Anspruchs Autorisierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="2c32e-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
<span data-ttu-id="2c32e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2c32e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2c32e-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="2c32e-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="2c32e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2c32e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="2c32e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ClaimsAuthorizationManager->**</span><span class="sxs-lookup"><span data-stu-id="2c32e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c32e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c32e-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c32e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2c32e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c32e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c32e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c32e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2c32e-110">Attributes</span></span>  
  
|<span data-ttu-id="2c32e-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="2c32e-111">Attribute</span></span>|<span data-ttu-id="2c32e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c32e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c32e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2c32e-113">type</span></span>|<span data-ttu-id="2c32e-114">Ein benutzerdefinierter Typ, der von <xref:System.Security.Claims.ClaimsAuthorizationManager> der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2c32e-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="2c32e-115">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="2c32e-115">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c32e-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c32e-116">Child Elements</span></span>  
 <span data-ttu-id="2c32e-117">Wenn kein `type` -Attribut vorhanden ist, oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> auf die- `<claimsAuthorizationManager>` Klasse verweist, nimmt das-Element keine untergeordneten Elemente an <xref:System.Security.Claims.ClaimsAuthorizationManager> . von abgeleitete Klassen können jedoch untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="2c32e-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c32e-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c32e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2c32e-119">Element</span><span class="sxs-lookup"><span data-stu-id="2c32e-119">Element</span></span>|<span data-ttu-id="2c32e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c32e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c32e-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2c32e-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="2c32e-122">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="2c32e-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c32e-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c32e-123">Remarks</span></span>  
 <span data-ttu-id="2c32e-124">Das Standardverhalten, das durch <xref:System.Security.Claims.ClaimsAuthorizationManager> die-Klasse bereitgestellt wird, autorisiert immer eingehende Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="2c32e-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="2c32e-125">Wenn kein `type` -Attribut angegeben wird oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthorizationManager> die-Klasse `<claimsAuthorizationManager>` angibt, nimmt das-Element keine untergeordneten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="2c32e-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="2c32e-126">Sie können das `type` Attribut angeben, um einen von der <xref:System.Security.Claims.ClaimsAuthorizationManager> -Klasse abgeleiteten Typ zu registrieren, um benutzerdefiniertes Verhalten zu implementieren</span><span class="sxs-lookup"><span data-stu-id="2c32e-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="2c32e-127">Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente `<claimsAuthorizationManager>` des-Elements unter <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> stützen, indem Sie die-Methode zum Verarbeiten dieser Elemente überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2c32e-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="2c32e-128">Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2c32e-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2c32e-129">Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> die-Klasse verwenden, um eine Anspruchs basierte Zugriffs Steuerung im Code bereitzustellen, konfiguriert die Identitäts Konfiguration `<federationConfiguration>` , auf die das-Element verweist, den anspruchsautorisierungs-Manager und die Richtlinie, die verwendet wird, um Autorisierungs Entscheidungen.</span><span class="sxs-lookup"><span data-stu-id="2c32e-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="2c32e-130">Dies gilt auch für Szenarien, bei denen es sich nicht um passive Webszenarien handelt, z. b. Windows Communication Foundation (WCF)-Anwendungen oder eine nicht webbasierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c32e-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="2c32e-131">Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, `<claimsAuthorizationManager>` werden das-Element (und seine untergeordneten Richtlinien Elemente, falls vorhanden) der Identitäts Konfiguration, auf die verwiesen wird, als einzige Einstellung angewendet.</span><span class="sxs-lookup"><span data-stu-id="2c32e-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="2c32e-132">Alle anderen Einstellungen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2c32e-132">All other settings are ignored.</span></span> <span data-ttu-id="2c32e-133">Weitere Informationen finden Sie unter dem [ \<Element federationconfiguration >](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="2c32e-133">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="2c32e-134">Mit diesem Element wird <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> die-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2c32e-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c32e-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c32e-135">Example</span></span>  
 <span data-ttu-id="2c32e-136">Der folgende XML-Code zeigt die Konfiguration für einen anspruchsautorisierungs-Manager, der eine Richtlinie implementiert, die aus Ressourcen Aktions Paaren besteht, von denen jede boolesche Kombinationen der Ansprüche angibt, die ein Anforderer besitzen muss, um die Aktion für die Ressource auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2c32e-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="2c32e-137">Der Code, der den Anspruchs Autorisierungs-Manager implementiert, der diese Richtlinie verwenden kann `ClaimsBasedAuthorization` , finden Sie im Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2c32e-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
