---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251964"
---
# \<issuerNameRegistry>
<span data-ttu-id="a5df7-101">Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5df7-101">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a><span data-ttu-id="a5df7-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5df7-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5df7-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a5df7-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a5df7-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5df7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5df7-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="a5df7-105">Attributes</span></span>  
  
|<span data-ttu-id="a5df7-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a5df7-106">Attribute</span></span>|<span data-ttu-id="a5df7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a5df7-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5df7-108">type</span><span class="sxs-lookup"><span data-stu-id="a5df7-108">type</span></span>|<span data-ttu-id="a5df7-109">Ein Typ, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerNameRegistry> .</span><span class="sxs-lookup"><span data-stu-id="a5df7-109">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="a5df7-110">Weitere Informationen zum Angeben eines benutzerdefinierten finden Sie `type` unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="a5df7-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5df7-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5df7-111">Child Elements</span></span>  
  
|<span data-ttu-id="a5df7-112">Element</span><span class="sxs-lookup"><span data-stu-id="a5df7-112">Element</span></span>|<span data-ttu-id="a5df7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5df7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|<span data-ttu-id="a5df7-114">Wenn das- `type` Attribut die konfigurationsbasierte Aussteller Namen Registrierung (die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse) angibt, [\<trustedIssuers>](trustedissuers.md) muss das-Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5df7-114">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="a5df7-115">Das- [\<trustedIssuers>](trustedissuers.md) Element kann- `<add>` ,-oder- `<clear>` `<remove>` Elemente als untergeordnete Elemente annehmen.</span><span class="sxs-lookup"><span data-stu-id="a5df7-115">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5df7-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5df7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a5df7-117">Element</span><span class="sxs-lookup"><span data-stu-id="a5df7-117">Element</span></span>|<span data-ttu-id="a5df7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5df7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a5df7-119">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="a5df7-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5df7-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a5df7-120">Remarks</span></span>  
 <span data-ttu-id="a5df7-121">Alle Aussteller Token werden mithilfe der Aussteller Namen Registrierung überprüft.</span><span class="sxs-lookup"><span data-stu-id="a5df7-121">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="a5df7-122">Dies ist ein Objekt, das von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerNameRegistry> .</span><span class="sxs-lookup"><span data-stu-id="a5df7-122">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="a5df7-123">Die Aussteller Namen Registrierung wird verwendet, um einem kryptografiematerial, das zum Überprüfen der Signaturen von Token, die vom entsprechenden Aussteller erstellt werden, einen mnetmonischen Namen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a5df7-123">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="a5df7-124">Die Aussteller Namen Registrierung verwaltet eine Liste der Aussteller, die von der Anwendung der vertrauenden Seite als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="a5df7-124">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="a5df7-125">Der Typ der Aussteller Namen Registrierung wird mithilfe des- `type` Attributs angegeben.</span><span class="sxs-lookup"><span data-stu-id="a5df7-125">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="a5df7-126">Das- `<issuerNameRegistry>` Element kann ein oder mehrere untergeordnete-Elemente aufweisen, die die Konfiguration für den angegebenen Typ bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a5df7-126">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="a5df7-127">Die Logik, die diese untergeordneten Elemente verarbeitet, wird durch Überschreiben der-Methode bereitgestellt <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="a5df7-127">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="a5df7-128">WIF bietet standardmäßig einen Registrierungs Typ für einen einzelnen Aussteller Namen, die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a5df7-128">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="a5df7-129">Diese Klasse verwendet einen Satz vertrauenswürdiger Aussteller Zertifikate, die in der Konfiguration angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a5df7-129">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="a5df7-130">Hierfür ist ein untergeordnetes Konfigurationselement erforderlich, `<trustedIssuers>` unter dem die Sammlung vertrauenswürdiger Aussteller Zertifikate konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a5df7-130">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="a5df7-131">Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und der Auflistung mithilfe der `<add>` Elemente, oder hinzugefügt bzw. daraus entfernt `<clear>` `<remove>` .</span><span class="sxs-lookup"><span data-stu-id="a5df7-131">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="a5df7-132">Das- `<issuerNameRegistry>` Element wird durch die- <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a5df7-132">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5df7-133">Die Angabe des- `<issuerNameRegistry>` Elements als untergeordnetes Element des-Elements wurde als [\<identityConfiguration>](identityconfiguration.md) veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a5df7-133">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="a5df7-134">Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="a5df7-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5df7-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5df7-135">Example</span></span>  
 <span data-ttu-id="a5df7-136">Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a5df7-136">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5df7-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5df7-137">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
