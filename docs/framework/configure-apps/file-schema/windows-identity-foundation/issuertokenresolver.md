---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 08082d2e6647f07f33df72ab79dac00c15a1cd1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200817"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="b9209-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b9209-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="b9209-102">Registriert die Aussteller-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9209-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b9209-103">Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b9209-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b9209-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b9209-104">\<system.identityModel></span></span>  
<span data-ttu-id="b9209-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b9209-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b9209-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b9209-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b9209-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b9209-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b9209-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b9209-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9209-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9209-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9209-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9209-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9209-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9209-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9209-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9209-112">Attributes</span></span>  
  
|<span data-ttu-id="b9209-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b9209-113">Attribute</span></span>|<span data-ttu-id="b9209-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9209-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9209-115">Typ</span><span class="sxs-lookup"><span data-stu-id="b9209-115">type</span></span>|<span data-ttu-id="b9209-116">Gibt den Typ der Aussteller-tokenresolvers.</span><span class="sxs-lookup"><span data-stu-id="b9209-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b9209-117">Muss entweder die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9209-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b9209-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9209-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9209-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9209-119">Child Elements</span></span>  
 <span data-ttu-id="b9209-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="b9209-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9209-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9209-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b9209-122">Element</span><span class="sxs-lookup"><span data-stu-id="b9209-122">Element</span></span>|<span data-ttu-id="b9209-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9209-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9209-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b9209-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b9209-125">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b9209-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9209-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9209-126">Remarks</span></span>  
 <span data-ttu-id="b9209-127">Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b9209-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b9209-128">Es wird verwendet, um das kryptografische Material abzurufen, das für die Überprüfung der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9209-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b9209-129">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9209-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="b9209-130">Der angegebene Typ kann es sich entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9209-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b9209-131">Einige Tokenhandler können Sie Aussteller-tokenresolver Einstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9209-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b9209-132">Einstellungen für einzelne Tokenhandler außer Kraft setzen auf der Sicherheitstoken-Handlerauflistung angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9209-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9209-133">Angeben der `<issuerTokenResolver>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b9209-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b9209-134">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="b9209-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9209-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9209-135">Example</span></span>  
 <span data-ttu-id="b9209-136">Das folgende XML zeigt die Konfiguration für einen Aussteller-tokenresolver, der für eine benutzerdefinierte Klasse basiert, die von abgeleitet <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="b9209-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b9209-137">Der tokenresolver verwaltet ein Wörterbuch der Zielgruppe-Schlüssel-Paare, die über ein benutzerdefiniertes Konfigurationselement initialisiert wird (`<AddAudienceKeyPair>`) für die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="b9209-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b9209-138">Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b9209-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b9209-139">Die Außerkraftsetzung wurde im folgenden Beispiel dargestellt. Allerdings werden die Methoden, die er aufruft, aus Gründen der Übersichtlichkeit nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9209-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b9209-140">Das vollständige Beispiel finden Sie unter den `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b9209-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b9209-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9209-141">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9209-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9209-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
