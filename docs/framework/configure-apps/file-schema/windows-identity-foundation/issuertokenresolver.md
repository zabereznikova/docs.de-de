---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 946ae8601e1e4563becd0b346b6c792724405a45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165038"
---
# \<issuerTokenResolver>

<span data-ttu-id="e9328-101">Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e9328-101">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e9328-102">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="e9328-102">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="e9328-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9328-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9328-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9328-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e9328-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9328-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9328-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9328-106">Attributes</span></span>  
  
|<span data-ttu-id="e9328-107">attribute</span><span class="sxs-lookup"><span data-stu-id="e9328-107">Attribute</span></span>|<span data-ttu-id="e9328-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e9328-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9328-109">type</span><span class="sxs-lookup"><span data-stu-id="e9328-109">type</span></span>|<span data-ttu-id="e9328-110">Gibt den Typ des Aussteller-tokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="e9328-110">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e9328-111">Muss entweder die- <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ sein, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e9328-111">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e9328-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e9328-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9328-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9328-113">Child Elements</span></span>  

 <span data-ttu-id="e9328-114">Keine</span><span class="sxs-lookup"><span data-stu-id="e9328-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9328-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9328-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e9328-116">Element</span><span class="sxs-lookup"><span data-stu-id="e9328-116">Element</span></span>|<span data-ttu-id="e9328-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9328-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e9328-118">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="e9328-118">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9328-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9328-119">Remarks</span></span>  

 <span data-ttu-id="e9328-120">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="e9328-120">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e9328-121">Sie wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e9328-121">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e9328-122">Sie müssen das- `type` Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="e9328-122">You must specify the `type` attribute.</span></span> <span data-ttu-id="e9328-123">Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder ein benutzerdefinierter Typ sein, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e9328-123">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e9328-124">Einige Tokenhandler ermöglichen es Ihnen, Einstellungen für Aussteller-tokenresolver in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e9328-124">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e9328-125">Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.</span><span class="sxs-lookup"><span data-stu-id="e9328-125">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9328-126">Die Angabe des- `<issuerTokenResolver>` Elements als untergeordnetes Element des-Elements wurde als [\<identityConfiguration>](identityconfiguration.md) veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e9328-126">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e9328-127">Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="e9328-127">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9328-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9328-128">Example</span></span>  

 <span data-ttu-id="e9328-129">Der folgende XML-Code zeigt die Konfiguration für einen Aussteller-tokenresolver, der auf einer benutzerdefinierten Klasse basiert, die von abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e9328-129">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e9328-130">Der tokenresolver verwaltet ein Wörterbuch von Audience-Key-Paaren, die von einem benutzerdefinierten Konfigurationselement () initialisiert werden, das `<AddAudienceKeyPair>` für die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e9328-130">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e9328-131">Die-Klasse überschreibt die- <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e9328-131">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e9328-132">Die außer Kraft setzung wird im folgenden Beispiel gezeigt. die Methoden, die Sie aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9328-132">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e9328-133">Das gesamte Beispiel finden Sie im Beispiel `CustomToken` .</span><span class="sxs-lookup"><span data-stu-id="e9328-133">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e9328-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9328-134">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9328-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9328-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
