---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252166"
---
# <a name="audienceuris"></a><span data-ttu-id="a50e7-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="a50e7-101">\<audienceUris></span></span>
<span data-ttu-id="a50e7-102">Gibt den Satz von URIs an, die akzeptable Bezeichner der vertrauenden Seite (RP) sind.</span><span class="sxs-lookup"><span data-stu-id="a50e7-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="a50e7-103">Token werden nur akzeptiert, wenn Sie für eine der zulässigen Zielgruppen-URIs festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="a50e7-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="a50e7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a50e7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a50e7-105">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a50e7-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a50e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a50e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a50e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="a50e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="a50e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration->** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a50e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="a50e7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<audienceUris->**</span><span class="sxs-lookup"><span data-stu-id="a50e7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50e7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a50e7-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a50e7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a50e7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a50e7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a50e7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a50e7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a50e7-113">Attributes</span></span>  
  
|<span data-ttu-id="a50e7-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="a50e7-114">Attribute</span></span>|<span data-ttu-id="a50e7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a50e7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a50e7-116">Modus</span><span class="sxs-lookup"><span data-stu-id="a50e7-116">mode</span></span>|<span data-ttu-id="a50e7-117">Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> -Wert, der angibt, ob die Zielgruppen Einschränkung auf ein eingehendes Token angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a50e7-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="a50e7-118">Mögliche Werte sind "Always", "Never" und "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="a50e7-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="a50e7-119">Der Standardwert ist "Always".</span><span class="sxs-lookup"><span data-stu-id="a50e7-119">The default is "Always".</span></span> <span data-ttu-id="a50e7-120">Optional.</span><span class="sxs-lookup"><span data-stu-id="a50e7-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a50e7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a50e7-121">Child Elements</span></span>  
  
|<span data-ttu-id="a50e7-122">Element</span><span class="sxs-lookup"><span data-stu-id="a50e7-122">Element</span></span>|<span data-ttu-id="a50e7-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a50e7-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="a50e7-124">Fügt den URI, der vom `value` -Attribut angegeben wird, der audienceUris-Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a50e7-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="a50e7-125">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a50e7-125">The `value` attribute is required.</span></span> <span data-ttu-id="a50e7-126">Beim URI wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="a50e7-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="a50e7-127">Löscht die audienceUris-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a50e7-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="a50e7-128">Alle Bezeichner werden aus der Sammlung entfernt.</span><span class="sxs-lookup"><span data-stu-id="a50e7-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="a50e7-129">Entfernt den URI, der durch `value` das-Attribut aus der audienceUris-Auflistung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a50e7-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="a50e7-130">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a50e7-130">The `value` attribute is required.</span></span> <span data-ttu-id="a50e7-131">Beim URI wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="a50e7-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a50e7-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a50e7-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a50e7-133">Element</span><span class="sxs-lookup"><span data-stu-id="a50e7-133">Element</span></span>|<span data-ttu-id="a50e7-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a50e7-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a50e7-135">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="a50e7-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a50e7-136">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="a50e7-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a50e7-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a50e7-137">Remarks</span></span>  
 <span data-ttu-id="a50e7-138">Standardmäßig ist die Auflistung leer. verwenden `<add>`Sie `<clear>`die Elemente `<remove>` , und, um die Auflistung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a50e7-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="a50e7-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> und-Objekte verwenden die Werte in der Zielgruppen-URI-Auflistung, um alle <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> zulässigen Audience-URI-Einschränkungen in Objekten zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a50e7-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="a50e7-140">Das `<audienceUris>` -Element wird durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a50e7-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="a50e7-141">Ein einzelner URI, der der Auflistung hinzugefügt wird, <xref:System.IdentityModel.Configuration.AudienceUriElement> wird durch die-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a50e7-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a50e7-142">Die Verwendung des `<audienceUris>` -Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a50e7-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="a50e7-143">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="a50e7-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a50e7-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a50e7-144">Example</span></span>  
 <span data-ttu-id="a50e7-145">Der folgende XML-Code zeigt, wie die zulässigen Zielgruppen-URIs für eine Anwendung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a50e7-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="a50e7-146">In diesem Beispiel wird ein einzelner URI konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a50e7-146">This example configures a single URI.</span></span> <span data-ttu-id="a50e7-147">Token, die für diesen URI gelten, werden akzeptiert, alle anderen werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="a50e7-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
