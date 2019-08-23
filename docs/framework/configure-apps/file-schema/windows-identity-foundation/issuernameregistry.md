---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942668"
---
# <a name="issuernameregistry"></a><span data-ttu-id="d37b9-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d37b9-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="d37b9-102">Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d37b9-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="d37b9-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d37b9-103">\<system.identityModel></span></span>  
<span data-ttu-id="d37b9-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d37b9-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d37b9-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d37b9-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d37b9-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d37b9-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d37b9-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d37b9-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d37b9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d37b9-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d37b9-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d37b9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d37b9-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d37b9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d37b9-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d37b9-111">Attributes</span></span>  
  
|<span data-ttu-id="d37b9-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d37b9-112">Attribute</span></span>|<span data-ttu-id="d37b9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d37b9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d37b9-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d37b9-114">type</span></span>|<span data-ttu-id="d37b9-115">Ein Typ, der von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d37b9-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d37b9-116">Weitere Informationen zum Angeben eines benutzerdefinierten `type`finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="d37b9-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d37b9-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d37b9-117">Child Elements</span></span>  
  
|<span data-ttu-id="d37b9-118">Element</span><span class="sxs-lookup"><span data-stu-id="d37b9-118">Element</span></span>|<span data-ttu-id="d37b9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d37b9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d37b9-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="d37b9-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="d37b9-121">Wenn das `type` -Attribut die konfigurationsbasierte Aussteller Namen Registrierung (die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse) angibt, müssen die [ \<Treuhänder >](trustedissuers.md) -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d37b9-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="d37b9-122">`<clear>`Das `<remove>` `<add>` [ \<Element "Treuhänder >](trustedissuers.md) " kann-,-oder-Elemente als untergeordnete Elemente annehmen.</span><span class="sxs-lookup"><span data-stu-id="d37b9-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d37b9-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d37b9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d37b9-124">Element</span><span class="sxs-lookup"><span data-stu-id="d37b9-124">Element</span></span>|<span data-ttu-id="d37b9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d37b9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d37b9-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d37b9-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d37b9-127">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="d37b9-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d37b9-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d37b9-128">Remarks</span></span>  
 <span data-ttu-id="d37b9-129">Alle Aussteller Token werden mithilfe der Aussteller Namen Registrierung überprüft.</span><span class="sxs-lookup"><span data-stu-id="d37b9-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="d37b9-130">Dies ist ein Objekt, das von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d37b9-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d37b9-131">Die Aussteller Namen Registrierung wird verwendet, um einem kryptografiematerial, das zum Überprüfen der Signaturen von Token, die vom entsprechenden Aussteller erstellt werden, einen mnetmonischen Namen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d37b9-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="d37b9-132">Die Aussteller Namen Registrierung verwaltet eine Liste der Aussteller, die von der Anwendung der vertrauenden Seite als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="d37b9-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="d37b9-133">Der Typ der Aussteller Namen Registrierung wird mithilfe des `type` -Attributs angegeben.</span><span class="sxs-lookup"><span data-stu-id="d37b9-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="d37b9-134">Das `<issuerNameRegistry>` -Element kann ein oder mehrere untergeordnete-Elemente aufweisen, die die Konfiguration für den angegebenen Typ bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d37b9-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="d37b9-135">Die Logik, die diese untergeordneten Elemente verarbeitet, wird durch <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Überschreiben der-Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d37b9-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="d37b9-136">WIF bietet standardmäßig einen Registrierungs Typ für einen einzelnen Aussteller Namen, die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="d37b9-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d37b9-137">Diese Klasse verwendet einen Satz vertrauenswürdiger Aussteller Zertifikate, die in der Konfiguration angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d37b9-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="d37b9-138">Hierfür ist ein untergeordnetes Konfigurationselement `<trustedIssuers>`erforderlich, unter dem die Sammlung vertrauenswürdiger Aussteller Zertifikate konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d37b9-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="d37b9-139">Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und der Auflistung mithilfe `<add>`der Elemente, `<clear>`oder `<remove>` hinzugefügt bzw. daraus entfernt.</span><span class="sxs-lookup"><span data-stu-id="d37b9-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d37b9-140">Das `<issuerNameRegistry>` -Element wird durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d37b9-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d37b9-141">Die Angabe `<issuerNameRegistry>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d37b9-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d37b9-142">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="d37b9-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d37b9-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d37b9-143">Example</span></span>  
 <span data-ttu-id="d37b9-144">Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d37b9-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d37b9-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d37b9-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
