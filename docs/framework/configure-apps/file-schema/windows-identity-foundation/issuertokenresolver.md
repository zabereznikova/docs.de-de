---
title: '&lt;issuerTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e859f99768eae5c931618d5902caf40dfad95d54
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="f0baa-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="f0baa-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="f0baa-103">Registriert die Aussteller-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0baa-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f0baa-104">Die Aussteller-tokenresolver wird zum Auflösen von der signiertokens für eingehende Token und Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0baa-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="f0baa-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f0baa-105">\<system.identityModel></span></span>  
<span data-ttu-id="f0baa-106">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f0baa-106">\<identityConfiguration></span></span>  
<span data-ttu-id="f0baa-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="f0baa-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f0baa-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f0baa-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f0baa-109">\<IssuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="f0baa-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0baa-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0baa-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0baa-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0baa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f0baa-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0baa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0baa-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0baa-113">Attributes</span></span>  
  
|<span data-ttu-id="f0baa-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="f0baa-114">Attribute</span></span>|<span data-ttu-id="f0baa-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0baa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0baa-116">Typ</span><span class="sxs-lookup"><span data-stu-id="f0baa-116">type</span></span>|<span data-ttu-id="f0baa-117">Gibt den Typ des Ausstellers token Konfliktlösers.</span><span class="sxs-lookup"><span data-stu-id="f0baa-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="f0baa-118">Muss entweder der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0baa-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="f0baa-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f0baa-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0baa-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0baa-120">Child Elements</span></span>  
 <span data-ttu-id="f0baa-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="f0baa-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0baa-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0baa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f0baa-123">Element</span><span class="sxs-lookup"><span data-stu-id="f0baa-123">Element</span></span>|<span data-ttu-id="f0baa-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0baa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0baa-125">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f0baa-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="f0baa-126">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="f0baa-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0baa-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0baa-127">Remarks</span></span>  
 <span data-ttu-id="f0baa-128">Die Aussteller-tokenresolver wird zum Auflösen von der signiertokens für eingehende Token und Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0baa-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="f0baa-129">Es wird verwendet, um das kryptografische Material abzurufen, das für die Überprüfung der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0baa-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="f0baa-130">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="f0baa-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="f0baa-131">Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0baa-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="f0baa-132">Einige Tokenhandler können Sie token konfliktlösungseinstellungen der Aussteller in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="f0baa-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="f0baa-133">Einstellungen für einzelne Tokenhandler überschreiben für die Sicherheit Tokenhandler Auflistung angegebenen.</span><span class="sxs-lookup"><span data-stu-id="f0baa-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0baa-134">Angeben der `<issuerTokenResolver>` Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber noch für die Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0baa-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f0baa-135">Einstellungen auf der `<securityTokenHandlerConfiguration>` Element, überschreiben Sie die auf die `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="f0baa-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0baa-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0baa-136">Example</span></span>  
 <span data-ttu-id="f0baa-137">Das folgende XML zeigt die Konfiguration für einen Aussteller-Resolver, der für eine benutzerdefinierte Klasse basiert, die abgeleitet <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="f0baa-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="f0baa-138">Die tokenresolver verwaltet ein Wörterbuch der Zielgruppe-Schlüssel-Paare, die von einem benutzerdefinierten Konfiguration-Element initialisiert wird (`<AddAudienceKeyPair>`) für die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="f0baa-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="f0baa-139">Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f0baa-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="f0baa-140">Die Außerkraftsetzung wird im folgenden Beispiel gezeigt; Allerdings werden die aufgerufenen Methoden aus Gründen der Übersichtlichkeit nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0baa-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="f0baa-141">Das vollständige Beispiel finden Sie unter der `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f0baa-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="f0baa-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0baa-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0baa-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0baa-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
