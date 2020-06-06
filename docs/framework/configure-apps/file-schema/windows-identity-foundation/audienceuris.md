---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252166"
---
# \<audienceUris>
<span data-ttu-id="6a10f-101">Gibt den Satz von URIs an, die akzeptable Bezeichner der vertrauenden Seite (RP) sind.</span><span class="sxs-lookup"><span data-stu-id="6a10f-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="6a10f-102">Token werden nur akzeptiert, wenn sie im Bereich einer der zulässigen "Audience"-URIs liegen.</span><span class="sxs-lookup"><span data-stu-id="6a10f-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="6a10f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a10f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a10f-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6a10f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="6a10f-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a10f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a10f-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="6a10f-106">Attributes</span></span>  
  
|<span data-ttu-id="6a10f-107">attribute</span><span class="sxs-lookup"><span data-stu-id="6a10f-107">Attribute</span></span>|<span data-ttu-id="6a10f-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a10f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a10f-109">Modus</span><span class="sxs-lookup"><span data-stu-id="6a10f-109">mode</span></span>|<span data-ttu-id="6a10f-110">Ein- <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die Zielgruppen Einschränkung auf ein eingehendes Token angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a10f-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="6a10f-111">Mögliche Werte sind "Always", "Never" und "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="6a10f-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="6a10f-112">Der Standardwert ist "Always".</span><span class="sxs-lookup"><span data-stu-id="6a10f-112">The default is "Always".</span></span> <span data-ttu-id="6a10f-113">(Optional)</span><span class="sxs-lookup"><span data-stu-id="6a10f-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a10f-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a10f-114">Child Elements</span></span>  
  
|<span data-ttu-id="6a10f-115">Element</span><span class="sxs-lookup"><span data-stu-id="6a10f-115">Element</span></span>|<span data-ttu-id="6a10f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a10f-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="6a10f-117">Fügt den URI, der vom- `value` Attribut angegeben wird, der audienceUris-Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a10f-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="6a10f-118">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a10f-118">The `value` attribute is required.</span></span> <span data-ttu-id="6a10f-119">Beim URI wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="6a10f-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="6a10f-120">Löscht die audienceUris-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6a10f-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="6a10f-121">Alle Bezeichner werden aus der Sammlung entfernt.</span><span class="sxs-lookup"><span data-stu-id="6a10f-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="6a10f-122">Entfernt den URI, der durch das- `value` Attribut aus der audienceUris-Auflistung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6a10f-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="6a10f-123">Das `value`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a10f-123">The `value` attribute is required.</span></span> <span data-ttu-id="6a10f-124">Beim URI wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="6a10f-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a10f-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a10f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6a10f-126">Element</span><span class="sxs-lookup"><span data-stu-id="6a10f-126">Element</span></span>|<span data-ttu-id="6a10f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a10f-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="6a10f-128">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="6a10f-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a10f-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6a10f-129">Remarks</span></span>  
 <span data-ttu-id="6a10f-130">Standardmäßig ist die Auflistung leer. verwenden `<add>` `<clear>` `<remove>` Sie die Elemente, und, um die Auflistung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6a10f-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="6a10f-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>-und- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Objekte verwenden die Werte in der Zielgruppen-URI-Auflistung, um alle zulässigen Audience-URI-Einschränkungen in Objekten zu konfigurieren <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="6a10f-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="6a10f-132">Das- `<audienceUris>` Element wird durch die- <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6a10f-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="6a10f-133">Ein einzelner URI, der der Auflistung hinzugefügt wird, wird durch die- <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6a10f-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a10f-134">Die Verwendung des- `<audienceUris>` Elements als untergeordnetes Element des- [\<identityConfiguration>](identityconfiguration.md) Elements wurde als veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6a10f-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="6a10f-135">Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="6a10f-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a10f-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a10f-136">Example</span></span>  
 <span data-ttu-id="6a10f-137">Der folgende XML-Code zeigt, wie die zulässigen Zielgruppen-URIs für eine Anwendung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6a10f-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="6a10f-138">In diesem Beispiel wird ein einzelner URI konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6a10f-138">This example configures a single URI.</span></span> <span data-ttu-id="6a10f-139">Token, die für diesen URI gelten, werden akzeptiert, alle anderen werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="6a10f-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
