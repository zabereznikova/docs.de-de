---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251964"
---
# <a name="issuernameregistry"></a><span data-ttu-id="81c99-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="81c99-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="81c99-102">Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="81c99-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
<span data-ttu-id="81c99-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81c99-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81c99-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="81c99-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="81c99-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="81c99-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="81c99-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="81c99-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="81c99-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration->** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="81c99-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="81c99-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerNameRegistry->**</span><span class="sxs-lookup"><span data-stu-id="81c99-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c99-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="81c99-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81c99-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="81c99-110">Attributes and Elements</span></span>  
 <span data-ttu-id="81c99-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81c99-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81c99-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="81c99-112">Attributes</span></span>  
  
|<span data-ttu-id="81c99-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="81c99-113">Attribute</span></span>|<span data-ttu-id="81c99-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81c99-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81c99-115">Typ</span><span class="sxs-lookup"><span data-stu-id="81c99-115">type</span></span>|<span data-ttu-id="81c99-116">Ein Typ, der von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="81c99-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="81c99-117">Weitere Informationen zum Angeben eines benutzerdefinierten `type`finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="81c99-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81c99-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="81c99-118">Child Elements</span></span>  
  
|<span data-ttu-id="81c99-119">Element</span><span class="sxs-lookup"><span data-stu-id="81c99-119">Element</span></span>|<span data-ttu-id="81c99-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81c99-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81c99-121">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="81c99-121">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="81c99-122">Wenn das `type` -Attribut die konfigurationsbasierte Aussteller Namen Registrierung (die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse) angibt, müssen die [ \<Treuhänder >](trustedissuers.md) -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="81c99-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="81c99-123">`<clear>`Das `<remove>` `<add>` [ \<Element "Treuhänder >](trustedissuers.md) " kann-,-oder-Elemente als untergeordnete Elemente annehmen.</span><span class="sxs-lookup"><span data-stu-id="81c99-123">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81c99-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="81c99-124">Parent Elements</span></span>  
  
|<span data-ttu-id="81c99-125">Element</span><span class="sxs-lookup"><span data-stu-id="81c99-125">Element</span></span>|<span data-ttu-id="81c99-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81c99-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81c99-127">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="81c99-127">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="81c99-128">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="81c99-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81c99-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81c99-129">Remarks</span></span>  
 <span data-ttu-id="81c99-130">Alle Aussteller Token werden mithilfe der Aussteller Namen Registrierung überprüft.</span><span class="sxs-lookup"><span data-stu-id="81c99-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="81c99-131">Dies ist ein Objekt, das von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="81c99-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="81c99-132">Die Aussteller Namen Registrierung wird verwendet, um einem kryptografiematerial, das zum Überprüfen der Signaturen von Token, die vom entsprechenden Aussteller erstellt werden, einen mnetmonischen Namen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="81c99-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="81c99-133">Die Aussteller Namen Registrierung verwaltet eine Liste der Aussteller, die von der Anwendung der vertrauenden Seite als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="81c99-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="81c99-134">Der Typ der Aussteller Namen Registrierung wird mithilfe des `type` -Attributs angegeben.</span><span class="sxs-lookup"><span data-stu-id="81c99-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="81c99-135">Das `<issuerNameRegistry>` -Element kann ein oder mehrere untergeordnete-Elemente aufweisen, die die Konfiguration für den angegebenen Typ bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="81c99-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="81c99-136">Die Logik, die diese untergeordneten Elemente verarbeitet, wird durch <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Überschreiben der-Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="81c99-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="81c99-137">WIF bietet standardmäßig einen Registrierungs Typ für einen einzelnen Aussteller Namen, die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="81c99-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="81c99-138">Diese Klasse verwendet einen Satz vertrauenswürdiger Aussteller Zertifikate, die in der Konfiguration angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="81c99-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="81c99-139">Hierfür ist ein untergeordnetes Konfigurationselement `<trustedIssuers>`erforderlich, unter dem die Sammlung vertrauenswürdiger Aussteller Zertifikate konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="81c99-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="81c99-140">Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und der Auflistung mithilfe `<add>`der Elemente, `<clear>`oder `<remove>` hinzugefügt bzw. daraus entfernt.</span><span class="sxs-lookup"><span data-stu-id="81c99-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="81c99-141">Das `<issuerNameRegistry>` -Element wird durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="81c99-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81c99-142">Die Angabe `<issuerNameRegistry>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81c99-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="81c99-143">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="81c99-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81c99-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81c99-144">Example</span></span>  
 <span data-ttu-id="81c99-145">Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="81c99-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81c99-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81c99-146">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
