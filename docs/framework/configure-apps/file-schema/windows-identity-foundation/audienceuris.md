---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: af138a4da49a48ed43e1bc8f2c2c81c56892feed
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082447"
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="26091-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="26091-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="26091-103">Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden Seite (RP) sind.</span><span class="sxs-lookup"><span data-stu-id="26091-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="26091-104">Token werden nicht akzeptiert werden, es sei denn, sie eines der zulässigen Audience-URI zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="26091-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="26091-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="26091-105">\<system.identityModel></span></span>  
<span data-ttu-id="26091-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="26091-106">\<identityConfiguration></span></span>  
<span data-ttu-id="26091-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="26091-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="26091-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="26091-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="26091-109">\<AudienceUris ></span><span class="sxs-lookup"><span data-stu-id="26091-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26091-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="26091-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26091-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26091-111">Attributes and Elements</span></span>  
 <span data-ttu-id="26091-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26091-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26091-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="26091-113">Attributes</span></span>  
  
|<span data-ttu-id="26091-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="26091-114">Attribute</span></span>|<span data-ttu-id="26091-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26091-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26091-116">mode</span><span class="sxs-lookup"><span data-stu-id="26091-116">mode</span></span>|<span data-ttu-id="26091-117">Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die zielgruppeneinschränkung auf ein eingehendes Token angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="26091-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="26091-118">Die möglichen Werte sind "Immer", "Never" und "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="26091-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="26091-119">Der Standardwert ist "Immer".</span><span class="sxs-lookup"><span data-stu-id="26091-119">The default is "Always".</span></span> <span data-ttu-id="26091-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="26091-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26091-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26091-121">Child Elements</span></span>  
  
|<span data-ttu-id="26091-122">Element</span><span class="sxs-lookup"><span data-stu-id="26091-122">Element</span></span>|<span data-ttu-id="26091-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26091-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="26091-124">Fügt den vom angegebenen URI die `value` -Attribut auf die Sammlung von AudienceUris.</span><span class="sxs-lookup"><span data-stu-id="26091-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="26091-125">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="26091-125">The `value` attribute is required.</span></span> <span data-ttu-id="26091-126">Der URI ist Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="26091-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="26091-127">Löscht die Auflistung von AudienceUris.</span><span class="sxs-lookup"><span data-stu-id="26091-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="26091-128">Alle Bezeichner werden aus der Auflistung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="26091-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="26091-129">Entfernt den angegebenen URI die `value` Attribut aus der Sammlung von AudienceUris.</span><span class="sxs-lookup"><span data-stu-id="26091-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="26091-130">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="26091-130">The `value` attribute is required.</span></span> <span data-ttu-id="26091-131">Der URI ist Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="26091-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26091-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26091-132">Parent Elements</span></span>  
  
|<span data-ttu-id="26091-133">Element</span><span class="sxs-lookup"><span data-stu-id="26091-133">Element</span></span>|<span data-ttu-id="26091-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26091-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26091-135">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="26091-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="26091-136">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="26091-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26091-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26091-137">Remarks</span></span>  
 <span data-ttu-id="26091-138">Standardmäßig ist die Auflistung leer. Verwenden Sie `<add>`, `<clear>`, und `<remove>` Elementen, die die Auflistung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="26091-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="26091-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> und <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Objekte verwenden, die die Werte in der Zielgruppe URI-Auflistung so konfigurieren Sie eine Zielgruppe URI-Einschränkungen in zulässige <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="26091-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="26091-140">Die `<audienceUris>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="26091-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="26091-141">Ein einzelner URI der Auflistung hinzugefügt wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="26091-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26091-142">Die Verwendung der `<audienceUris>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26091-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="26091-143">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="26091-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26091-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26091-144">Example</span></span>  
 <span data-ttu-id="26091-145">Das folgende XML zeigt, wie Sie die zulässigen Audience-URI für eine Anwendung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="26091-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="26091-146">In diesem Beispiel wird einen einzigen URI.</span><span class="sxs-lookup"><span data-stu-id="26091-146">This example configures a single URI.</span></span> <span data-ttu-id="26091-147">Akzeptiert Token, die für diesen URI beschränkt, alle anderen werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="26091-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
