---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 646833f277c3ef4675a835ca0af3daf647e01224
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="b33d8-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="b33d8-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="b33d8-103">Registriert die Aussteller-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b33d8-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b33d8-104">Die Aussteller-tokenresolver wird zum Auflösen von der signiertokens für eingehende Token und Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b33d8-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b33d8-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b33d8-105">\<system.identityModel></span></span>  
<span data-ttu-id="b33d8-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b33d8-106">\<identityConfiguration></span></span>  
<span data-ttu-id="b33d8-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b33d8-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b33d8-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b33d8-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b33d8-109">\<IssuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b33d8-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b33d8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b33d8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b33d8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b33d8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b33d8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b33d8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b33d8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b33d8-113">Attributes</span></span>  
  
|<span data-ttu-id="b33d8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b33d8-114">Attribute</span></span>|<span data-ttu-id="b33d8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b33d8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b33d8-116">Typ</span><span class="sxs-lookup"><span data-stu-id="b33d8-116">type</span></span>|<span data-ttu-id="b33d8-117">Gibt den Typ des Ausstellers token Konfliktlösers.</span><span class="sxs-lookup"><span data-stu-id="b33d8-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b33d8-118">Muss entweder der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b33d8-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b33d8-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b33d8-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b33d8-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b33d8-120">Child Elements</span></span>  
 <span data-ttu-id="b33d8-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="b33d8-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b33d8-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b33d8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b33d8-123">Element</span><span class="sxs-lookup"><span data-stu-id="b33d8-123">Element</span></span>|<span data-ttu-id="b33d8-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b33d8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b33d8-125">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b33d8-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b33d8-126">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b33d8-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b33d8-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b33d8-127">Remarks</span></span>  
 <span data-ttu-id="b33d8-128">Die Aussteller-tokenresolver wird zum Auflösen von der signiertokens für eingehende Token und Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b33d8-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b33d8-129">Es wird verwendet, um das kryptografische Material abzurufen, das für die Überprüfung der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b33d8-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b33d8-130">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="b33d8-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="b33d8-131">Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b33d8-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b33d8-132">Einige Tokenhandler können Sie token konfliktlösungseinstellungen der Aussteller in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="b33d8-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b33d8-133">Einstellungen für einzelne Tokenhandler überschreiben für die Sicherheit Tokenhandler Auflistung angegebenen.</span><span class="sxs-lookup"><span data-stu-id="b33d8-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b33d8-134">Angeben der `<issuerTokenResolver>` Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber noch für die Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b33d8-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b33d8-135">Einstellungen auf der `<securityTokenHandlerConfiguration>` Element, überschreiben Sie die auf die `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="b33d8-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b33d8-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b33d8-136">Example</span></span>  
 <span data-ttu-id="b33d8-137">Das folgende XML zeigt die Konfiguration für einen Aussteller-Resolver, der für eine benutzerdefinierte Klasse basiert, die abgeleitet <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="b33d8-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b33d8-138">Die tokenresolver verwaltet ein Wörterbuch der Zielgruppe-Schlüssel-Paare, die von einem benutzerdefinierten Konfiguration-Element initialisiert wird (`<AddAudienceKeyPair>`) für die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="b33d8-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b33d8-139">Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b33d8-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b33d8-140">Die Außerkraftsetzung wird im folgenden Beispiel gezeigt; Allerdings werden die aufgerufenen Methoden aus Gründen der Übersichtlichkeit nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b33d8-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b33d8-141">Das vollständige Beispiel finden Sie unter der `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b33d8-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b33d8-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b33d8-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b33d8-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b33d8-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
