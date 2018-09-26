---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: eefd18c206b7f013c3a423df424c795583c0dde8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216330"
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="217f7-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="217f7-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="217f7-103">Registriert die Aussteller-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="217f7-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="217f7-104">Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="217f7-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="217f7-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="217f7-105">\<system.identityModel></span></span>  
<span data-ttu-id="217f7-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="217f7-106">\<identityConfiguration></span></span>  
<span data-ttu-id="217f7-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="217f7-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="217f7-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="217f7-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="217f7-109">\<IssuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="217f7-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="217f7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="217f7-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="217f7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="217f7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="217f7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="217f7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="217f7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="217f7-113">Attributes</span></span>  
  
|<span data-ttu-id="217f7-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="217f7-114">Attribute</span></span>|<span data-ttu-id="217f7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="217f7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="217f7-116">Typ</span><span class="sxs-lookup"><span data-stu-id="217f7-116">type</span></span>|<span data-ttu-id="217f7-117">Gibt den Typ der Aussteller-tokenresolvers.</span><span class="sxs-lookup"><span data-stu-id="217f7-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="217f7-118">Muss entweder die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="217f7-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="217f7-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="217f7-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="217f7-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="217f7-120">Child Elements</span></span>  
 <span data-ttu-id="217f7-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="217f7-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="217f7-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="217f7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="217f7-123">Element</span><span class="sxs-lookup"><span data-stu-id="217f7-123">Element</span></span>|<span data-ttu-id="217f7-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="217f7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="217f7-125">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="217f7-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="217f7-126">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="217f7-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="217f7-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="217f7-127">Remarks</span></span>  
 <span data-ttu-id="217f7-128">Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="217f7-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="217f7-129">Es wird verwendet, um das kryptografische Material abzurufen, das für die Überprüfung der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="217f7-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="217f7-130">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="217f7-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="217f7-131">Der angegebene Typ kann es sich entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="217f7-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="217f7-132">Einige Tokenhandler können Sie Aussteller-tokenresolver Einstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="217f7-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="217f7-133">Einstellungen für einzelne Tokenhandler außer Kraft setzen auf der Sicherheitstoken-Handlerauflistung angegeben.</span><span class="sxs-lookup"><span data-stu-id="217f7-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="217f7-134">Angeben der `<issuerTokenResolver>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="217f7-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="217f7-135">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="217f7-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="217f7-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="217f7-136">Example</span></span>  
 <span data-ttu-id="217f7-137">Das folgende XML zeigt die Konfiguration für einen Aussteller-tokenresolver, der für eine benutzerdefinierte Klasse basiert, die von abgeleitet <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="217f7-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="217f7-138">Der tokenresolver verwaltet ein Wörterbuch der Zielgruppe-Schlüssel-Paare, die über ein benutzerdefiniertes Konfigurationselement initialisiert wird (`<AddAudienceKeyPair>`) für die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="217f7-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="217f7-139">Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="217f7-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="217f7-140">Die Außerkraftsetzung wurde im folgenden Beispiel dargestellt. Allerdings werden die Methoden, die er aufruft, aus Gründen der Übersichtlichkeit nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="217f7-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="217f7-141">Das vollständige Beispiel finden Sie unter den `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="217f7-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="217f7-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="217f7-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="217f7-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="217f7-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
