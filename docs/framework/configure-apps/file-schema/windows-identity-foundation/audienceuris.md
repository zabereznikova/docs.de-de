---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750747"
---
# <a name="audienceuris"></a><span data-ttu-id="0a8a2-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="0a8a2-101">\<audienceUris></span></span>
<span data-ttu-id="0a8a2-102">Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden Seite (RP) sind.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="0a8a2-103">Token werden nicht akzeptiert werden, es sei denn, sie eines der zulässigen Audience-URI zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="0a8a2-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0a8a2-104">\<system.identityModel></span></span>  
<span data-ttu-id="0a8a2-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0a8a2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="0a8a2-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="0a8a2-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="0a8a2-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="0a8a2-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="0a8a2-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="0a8a2-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8a2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a8a2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a8a2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a8a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0a8a2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a8a2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a8a2-112">Attributes</span></span>  
  
|<span data-ttu-id="0a8a2-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0a8a2-113">Attribute</span></span>|<span data-ttu-id="0a8a2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a8a2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a8a2-115">Modus</span><span class="sxs-lookup"><span data-stu-id="0a8a2-115">mode</span></span>|<span data-ttu-id="0a8a2-116">Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die zielgruppeneinschränkung auf ein eingehendes Token angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="0a8a2-117">Die möglichen Werte sind "Immer", "Never" und "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="0a8a2-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="0a8a2-118">Der Standardwert ist "Immer".</span><span class="sxs-lookup"><span data-stu-id="0a8a2-118">The default is "Always".</span></span> <span data-ttu-id="0a8a2-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a8a2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a8a2-120">Child Elements</span></span>  
  
|<span data-ttu-id="0a8a2-121">Element</span><span class="sxs-lookup"><span data-stu-id="0a8a2-121">Element</span></span>|<span data-ttu-id="0a8a2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a8a2-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="0a8a2-123">Fügt den vom angegebenen URI die `value` -Attribut auf die Sammlung von AudienceUris.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="0a8a2-124">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-124">The `value` attribute is required.</span></span> <span data-ttu-id="0a8a2-125">Der URI ist Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="0a8a2-126">Löscht die Auflistung von AudienceUris.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="0a8a2-127">Alle Bezeichner werden aus der Auflistung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="0a8a2-128">Entfernt den angegebenen URI die `value` Attribut aus der Sammlung von AudienceUris.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="0a8a2-129">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-129">The `value` attribute is required.</span></span> <span data-ttu-id="0a8a2-130">Der URI ist Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a8a2-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a8a2-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0a8a2-132">Element</span><span class="sxs-lookup"><span data-stu-id="0a8a2-132">Element</span></span>|<span data-ttu-id="0a8a2-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a8a2-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a8a2-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="0a8a2-134">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="0a8a2-135">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a8a2-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a8a2-136">Remarks</span></span>  
 <span data-ttu-id="0a8a2-137">Standardmäßig ist die Auflistung leer. Verwenden Sie `<add>`, `<clear>`, und `<remove>` Elementen, die die Auflistung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="0a8a2-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> und <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Objekte verwenden, die die Werte in der Zielgruppe URI-Auflistung so konfigurieren Sie eine Zielgruppe URI-Einschränkungen in zulässige <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="0a8a2-139">Die `<audienceUris>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="0a8a2-140">Ein einzelner URI der Auflistung hinzugefügt wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a8a2-141">Die Verwendung der `<audienceUris>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="0a8a2-142">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a8a2-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a8a2-143">Example</span></span>  
 <span data-ttu-id="0a8a2-144">Das folgende XML zeigt, wie Sie die zulässigen Audience-URI für eine Anwendung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="0a8a2-145">In diesem Beispiel wird einen einzigen URI.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-145">This example configures a single URI.</span></span> <span data-ttu-id="0a8a2-146">Akzeptiert Token, die für diesen URI beschränkt, alle anderen werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="0a8a2-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
