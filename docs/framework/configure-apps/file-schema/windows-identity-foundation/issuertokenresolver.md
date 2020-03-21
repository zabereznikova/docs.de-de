---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152670"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="85283-101">\<IssuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="85283-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="85283-102">Registriert den Ausstellertokenlöser, der von Handlern in der Tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85283-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="85283-103">Der Ausstellertokenlöser wird verwendet, um das Signaturtoken für eingehende Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="85283-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="85283-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85283-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85283-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="85283-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="85283-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="85283-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="85283-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="85283-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="85283-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="85283-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="85283-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<IssuerTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="85283-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85283-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="85283-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85283-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="85283-111">Attributes and Elements</span></span>  
 <span data-ttu-id="85283-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85283-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85283-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="85283-113">Attributes</span></span>  
  
|<span data-ttu-id="85283-114">attribute</span><span class="sxs-lookup"><span data-stu-id="85283-114">Attribute</span></span>|<span data-ttu-id="85283-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85283-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85283-116">type</span><span class="sxs-lookup"><span data-stu-id="85283-116">type</span></span>|<span data-ttu-id="85283-117">Gibt den Typ des Ausstellertokenlösers an.</span><span class="sxs-lookup"><span data-stu-id="85283-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="85283-118">Es muss <xref:System.IdentityModel.Tokens.IssuerTokenResolver> entweder die Klasse oder ein <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Typ sein, der von der Klasse stammt.</span><span class="sxs-lookup"><span data-stu-id="85283-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="85283-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85283-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85283-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85283-120">Child Elements</span></span>  
 <span data-ttu-id="85283-121">Keine</span><span class="sxs-lookup"><span data-stu-id="85283-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85283-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85283-122">Parent Elements</span></span>  
  
|<span data-ttu-id="85283-123">Element</span><span class="sxs-lookup"><span data-stu-id="85283-123">Element</span></span>|<span data-ttu-id="85283-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85283-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85283-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="85283-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="85283-126">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="85283-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85283-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="85283-127">Remarks</span></span>  
 <span data-ttu-id="85283-128">Der Ausstellertokenlöser wird verwendet, um das Signaturtoken für eingehende Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="85283-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="85283-129">Es wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85283-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="85283-130">Sie müssen `type` das Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="85283-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="85283-131">Der angegebene Typ <xref:System.IdentityModel.Tokens.IssuerTokenResolver> kann entweder oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse abstammt.</span><span class="sxs-lookup"><span data-stu-id="85283-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="85283-132">Einige Tokenhandler ermöglichen es Ihnen, Ausstellertoken-Resolvereinstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="85283-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="85283-133">Einstellungen für einzelne Tokenhandler überschreiben die in der Sicherheitstokenhandlerauflistung angegebenen.</span><span class="sxs-lookup"><span data-stu-id="85283-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85283-134">Die Angabe `<issuerTokenResolver>` des Elements als untergeordnetes Element der [ \<identityConfiguration>-Element](identityconfiguration.md) sprägiert, wird aber aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85283-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="85283-135">Einstellungen für `<securityTokenHandlerConfiguration>` das Element überschreiben die Einstellungen für das `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="85283-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85283-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85283-136">Example</span></span>  
 <span data-ttu-id="85283-137">Der folgende XML-Code zeigt die Konfiguration für einen Ausstellertokenlöser, <xref:System.IdentityModel.Tokens.IssuerTokenResolver>der auf einer benutzerdefinierten Klasse basiert, die von ableitet.</span><span class="sxs-lookup"><span data-stu-id="85283-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="85283-138">Der Token-Resolver verwaltet ein Wörterbuch von Zielgruppen-Schlüsselpaaren,`<AddAudienceKeyPair>`das aus einem benutzerdefinierten Konfigurationselement ( ) initialisiert wird, das für die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="85283-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="85283-139">Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode zum Verarbeiten dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="85283-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="85283-140">Die Außerkraftsetzung wird im folgenden Beispiel gezeigt. Die Methoden, die es aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85283-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="85283-141">Das vollständige Beispiel finden `CustomToken` Sie im Beispiel.</span><span class="sxs-lookup"><span data-stu-id="85283-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="85283-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85283-142">Example</span></span>
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="85283-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85283-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
