---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941956"
---
# <a name="audienceuris"></a><span data-ttu-id="2e418-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="2e418-101">\<audienceUris></span></span>
<span data-ttu-id="2e418-102">Gibt den Satz von URIs an, die akzeptable Bezeichner der vertrauenden Seite (RP) sind.</span><span class="sxs-lookup"><span data-stu-id="2e418-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="2e418-103">Token werden nur akzeptiert, wenn Sie für eine der zulässigen Zielgruppen-URIs festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2e418-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="2e418-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2e418-104">\<system.identityModel></span></span>  
<span data-ttu-id="2e418-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2e418-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2e418-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="2e418-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2e418-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="2e418-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="2e418-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="2e418-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e418-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e418-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e418-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e418-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e418-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e418-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e418-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e418-112">Attributes</span></span>  
  
|<span data-ttu-id="2e418-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2e418-113">Attribute</span></span>|<span data-ttu-id="2e418-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e418-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e418-115">Modus</span><span class="sxs-lookup"><span data-stu-id="2e418-115">mode</span></span>|<span data-ttu-id="2e418-116">Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> -Wert, der angibt, ob die Zielgruppen Einschränkung auf ein eingehendes Token angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e418-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="2e418-117">Mögliche Werte sind "Always", "Never" und "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="2e418-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="2e418-118">Der Standardwert ist "Always".</span><span class="sxs-lookup"><span data-stu-id="2e418-118">The default is "Always".</span></span> <span data-ttu-id="2e418-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="2e418-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e418-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e418-120">Child Elements</span></span>  
  
|<span data-ttu-id="2e418-121">Element</span><span class="sxs-lookup"><span data-stu-id="2e418-121">Element</span></span>|<span data-ttu-id="2e418-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e418-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="2e418-123">Fügt den URI, der vom `value` -Attribut angegeben wird, der audienceUris-Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e418-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="2e418-124">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e418-124">The `value` attribute is required.</span></span> <span data-ttu-id="2e418-125">Beim URI wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="2e418-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="2e418-126">Löscht die audienceUris-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2e418-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="2e418-127">Alle Bezeichner werden aus der Sammlung entfernt.</span><span class="sxs-lookup"><span data-stu-id="2e418-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="2e418-128">Entfernt den URI, der durch `value` das-Attribut aus der audienceUris-Auflistung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2e418-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="2e418-129">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e418-129">The `value` attribute is required.</span></span> <span data-ttu-id="2e418-130">Beim URI wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="2e418-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e418-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e418-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2e418-132">Element</span><span class="sxs-lookup"><span data-stu-id="2e418-132">Element</span></span>|<span data-ttu-id="2e418-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e418-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e418-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="2e418-134">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="2e418-135">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="2e418-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e418-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e418-136">Remarks</span></span>  
 <span data-ttu-id="2e418-137">Standardmäßig ist die Auflistung leer. verwenden `<add>`Sie `<clear>`die Elemente `<remove>` , und, um die Auflistung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2e418-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="2e418-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> und-Objekte verwenden die Werte in der Zielgruppen-URI-Auflistung, um alle <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> zulässigen Audience-URI-Einschränkungen in Objekten zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2e418-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="2e418-139">Das `<audienceUris>` -Element wird durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2e418-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="2e418-140">Ein einzelner URI, der der Auflistung hinzugefügt wird, <xref:System.IdentityModel.Configuration.AudienceUriElement> wird durch die-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2e418-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e418-141">Die Verwendung des `<audienceUris>` -Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e418-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="2e418-142">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="2e418-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e418-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e418-143">Example</span></span>  
 <span data-ttu-id="2e418-144">Der folgende XML-Code zeigt, wie die zulässigen Zielgruppen-URIs für eine Anwendung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2e418-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="2e418-145">In diesem Beispiel wird ein einzelner URI konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2e418-145">This example configures a single URI.</span></span> <span data-ttu-id="2e418-146">Token, die für diesen URI gelten, werden akzeptiert, alle anderen werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="2e418-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
