---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968514"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="d8ec2-101">\<issuertokenresolver ></span><span class="sxs-lookup"><span data-stu-id="d8ec2-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="d8ec2-102">Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d8ec2-103">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="d8ec2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8ec2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d8ec2-105">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d8ec2-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d8ec2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d8ec2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d8ec2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d8ec2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d8ec2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d8ec2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="d8ec2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuertokenresolver >**</span><span class="sxs-lookup"><span data-stu-id="d8ec2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ec2-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8ec2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8ec2-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d8ec2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d8ec2-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8ec2-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8ec2-113">Attributes</span></span>  
  
|<span data-ttu-id="d8ec2-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="d8ec2-114">Attribute</span></span>|<span data-ttu-id="d8ec2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8ec2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8ec2-116">Typ</span><span class="sxs-lookup"><span data-stu-id="d8ec2-116">type</span></span>|<span data-ttu-id="d8ec2-117">Gibt den Typ des Aussteller-tokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="d8ec2-118">Muss entweder die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="d8ec2-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8ec2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8ec2-120">Child Elements</span></span>  
 <span data-ttu-id="d8ec2-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="d8ec2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8ec2-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8ec2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d8ec2-123">Element</span><span class="sxs-lookup"><span data-stu-id="d8ec2-123">Element</span></span>|<span data-ttu-id="d8ec2-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8ec2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8ec2-125">\<securitytokenhandlerconfiguration ></span><span class="sxs-lookup"><span data-stu-id="d8ec2-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d8ec2-126">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8ec2-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8ec2-127">Remarks</span></span>  
 <span data-ttu-id="d8ec2-128">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="d8ec2-129">Sie wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="d8ec2-130">Sie müssen das `type`-Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="d8ec2-131">Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver>-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="d8ec2-132">Einige Tokenhandler ermöglichen es Ihnen, Einstellungen für Aussteller-tokenresolver in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="d8ec2-133">Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8ec2-134">Das Angeben des `<issuerTokenResolver>`-Elements als untergeordnetes Element des [\<identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d8ec2-135">Die Einstellungen für das `<securityTokenHandlerConfiguration>` Element überschreiben die für das `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ec2-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8ec2-136">Example</span></span>  
 <span data-ttu-id="d8ec2-137">Der folgende XML-Code zeigt die Konfiguration für einen Aussteller-tokenresolver, der auf einer benutzerdefinierten Klasse basiert, die von <xref:System.IdentityModel.Tokens.IssuerTokenResolver>abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="d8ec2-138">Der tokenresolver verwaltet ein Wörterbuch von Audience-Key-Paaren, die von einem benutzerdefinierten Konfigurationselement (`<AddAudienceKeyPair>`) initialisiert werden, das für die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="d8ec2-139">Die-Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>-Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="d8ec2-140">Die außer Kraft setzung wird im folgenden Beispiel gezeigt. die Methoden, die Sie aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="d8ec2-141">Das gesamte Beispiel finden Sie im `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d8ec2-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="d8ec2-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8ec2-142">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8ec2-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8ec2-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
