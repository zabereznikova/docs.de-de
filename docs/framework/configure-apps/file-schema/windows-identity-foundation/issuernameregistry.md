---
title: '&lt;"issuerNameRegistry"&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: de3ceb5d84d17307c69e9155834a0a584e6920a1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185913"
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="4135e-102">&lt;"issuerNameRegistry"&gt;</span><span class="sxs-lookup"><span data-stu-id="4135e-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="4135e-103">Konfiguriert die Ausstellernamen-Registrierung, die von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4135e-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="4135e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4135e-104">\<system.identityModel></span></span>  
<span data-ttu-id="4135e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4135e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="4135e-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="4135e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4135e-107">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="4135e-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="4135e-108">\<"issuerNameRegistry" ></span><span class="sxs-lookup"><span data-stu-id="4135e-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4135e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4135e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4135e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4135e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4135e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4135e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4135e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="4135e-112">Attributes</span></span>  
  
|<span data-ttu-id="4135e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="4135e-113">Attribute</span></span>|<span data-ttu-id="4135e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4135e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4135e-115">Typ</span><span class="sxs-lookup"><span data-stu-id="4135e-115">type</span></span>|<span data-ttu-id="4135e-116">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4135e-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="4135e-117">Weitere Informationen zur Vorgehensweise beim Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="4135e-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4135e-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4135e-118">Child Elements</span></span>  
  
|<span data-ttu-id="4135e-119">Element</span><span class="sxs-lookup"><span data-stu-id="4135e-119">Element</span></span>|<span data-ttu-id="4135e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4135e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4135e-121">\<TrustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="4135e-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="4135e-122">Wenn die `type` Attribut gibt an, der konfigurationsbasierten ausstellernamenregistrierung (die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse), wird die [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4135e-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="4135e-123">Die [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element dauert `<add>`, `<clear>`, oder `<remove>` -Elemente als untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="4135e-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4135e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4135e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4135e-125">Element</span><span class="sxs-lookup"><span data-stu-id="4135e-125">Element</span></span>|<span data-ttu-id="4135e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4135e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4135e-127">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="4135e-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="4135e-128">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="4135e-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4135e-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4135e-129">Remarks</span></span>  
 <span data-ttu-id="4135e-130">Alle ausstellertoken werden überprüft, eine Ausstellernamen-Registrierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4135e-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="4135e-131">Dies ist ein Objekt, das von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4135e-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="4135e-132">Die Ausstellernamen-Registrierung wird verwendet, um einen merknamen kryptografischen Informationen zuzuordnen, die benötigt werden, um zu überprüfen, ob die Signaturen von Token, die vom entsprechenden Aussteller erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="4135e-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="4135e-133">Die Ausstellernamen-Registrierung verwaltet eine Liste der Zertifikataussteller, die die Anwendung der vertrauenden Seite (Relying Party, RP) vertraut.</span><span class="sxs-lookup"><span data-stu-id="4135e-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="4135e-134">Der Typ, der die Ausstellernamen-Registrierung angegeben ist, mit der `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="4135e-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="4135e-135">Die `<issuerNameRegistry>` -Element kann eine oder mehrere untergeordnete Elemente, die Konfiguration für den angegebenen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4135e-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="4135e-136">Geben Sie die Logik, die verarbeitet diese untergeordneten Elemente durch Überschreiben der <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="4135e-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="4135e-137">WIF stellt einen einzelnen Aussteller namens Registrierungstyp standardmäßig die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4135e-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="4135e-138">Diese Klasse verwendet eine Reihe von Zertifikaten vertrauenswürdiger Aussteller, die in der Konfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4135e-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="4135e-139">Es muss ein untergeordnetes Konfigurationselement `<trustedIssuers>`, unter dem die Auflistung von Zertifikaten vertrauenswürdiger Aussteller konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4135e-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="4135e-140">Vertrauenswürdige Zertifikate angegeben sind, mit der ASN. 1-codierte Form des Zertifikatfingerabdrucks und hinzugefügt oder aus der Auflistung entfernt werden, mithilfe von `<add>`, `<clear>`, oder `<remove>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="4135e-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="4135e-141">Die `<issuerNameRegistry>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4135e-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4135e-142">Angeben der `<issuerNameRegistry>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4135e-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="4135e-143">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="4135e-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4135e-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4135e-144">Example</span></span>  
 <span data-ttu-id="4135e-145">Das folgende XML zeigt, wie an den Aussteller für die Konfiguration basiert-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="4135e-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4135e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4135e-146">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
