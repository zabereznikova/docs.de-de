---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: da591940910b16d42ef8ab1a05c4b244dbe543f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942625"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="6b9fb-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6b9fb-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="6b9fb-102">Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6b9fb-103">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="6b9fb-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6b9fb-104">\<system.identityModel></span></span>  
<span data-ttu-id="6b9fb-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b9fb-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6b9fb-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6b9fb-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6b9fb-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b9fb-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="6b9fb-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6b9fb-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b9fb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b9fb-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b9fb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b9fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6b9fb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b9fb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b9fb-112">Attributes</span></span>  
  
|<span data-ttu-id="6b9fb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b9fb-113">Attribute</span></span>|<span data-ttu-id="6b9fb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b9fb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b9fb-115">Typ</span><span class="sxs-lookup"><span data-stu-id="6b9fb-115">type</span></span>|<span data-ttu-id="6b9fb-116">Gibt den Typ des Aussteller-tokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="6b9fb-117">Muss entweder die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> -Klasse oder ein Typ sein, der von <xref:System.IdentityModel.Tokens.IssuerTokenResolver> der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="6b9fb-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b9fb-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b9fb-119">Child Elements</span></span>  
 <span data-ttu-id="6b9fb-120">None</span><span class="sxs-lookup"><span data-stu-id="6b9fb-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b9fb-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b9fb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6b9fb-122">Element</span><span class="sxs-lookup"><span data-stu-id="6b9fb-122">Element</span></span>|<span data-ttu-id="6b9fb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b9fb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b9fb-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b9fb-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="6b9fb-125">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b9fb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b9fb-126">Remarks</span></span>  
 <span data-ttu-id="6b9fb-127">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="6b9fb-128">Sie wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="6b9fb-129">Sie müssen das `type` -Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="6b9fb-130">Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="6b9fb-131">Einige Tokenhandler ermöglichen es Ihnen, Einstellungen für Aussteller-tokenresolver in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="6b9fb-132">Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b9fb-133">Die Angabe `<issuerTokenResolver>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="6b9fb-134">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b9fb-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b9fb-135">Example</span></span>  
 <span data-ttu-id="6b9fb-136">Der folgende XML-Code zeigt die Konfiguration für einen Aussteller-tokenresolver, der auf einer Benutzer <xref:System.IdentityModel.Tokens.IssuerTokenResolver>definierten Klasse basiert, die von abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="6b9fb-137">Der tokenresolver verwaltet ein Wörterbuch von Audience-Key-Paaren, die von einem benutzerdefinierten Konfigurations`<AddAudienceKeyPair>`Element () initialisiert werden, das für die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="6b9fb-138">Die-Klasse überschreibt <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> die-Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="6b9fb-139">Die außer Kraft setzung wird im folgenden Beispiel gezeigt. die Methoden, die Sie aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="6b9fb-140">Das gesamte Beispiel finden Sie im `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6b9fb-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="6b9fb-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b9fb-141">Example</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="6b9fb-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b9fb-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
