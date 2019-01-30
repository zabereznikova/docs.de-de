---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: db4e0492772d6fd0e155843422b7350aa630f713
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269522"
---
# <a name="issuernameregistry"></a><span data-ttu-id="fdf8c-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="fdf8c-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="fdf8c-102">Konfiguriert die Ausstellernamen-Registrierung, die von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="fdf8c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fdf8c-103">\<system.identityModel></span></span>  
<span data-ttu-id="fdf8c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fdf8c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="fdf8c-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="fdf8c-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fdf8c-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="fdf8c-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="fdf8c-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="fdf8c-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf8c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdf8c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdf8c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fdf8c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fdf8c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdf8c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fdf8c-111">Attributes</span></span>  
  
|<span data-ttu-id="fdf8c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="fdf8c-112">Attribute</span></span>|<span data-ttu-id="fdf8c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdf8c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdf8c-114">Typ</span><span class="sxs-lookup"><span data-stu-id="fdf8c-114">type</span></span>|<span data-ttu-id="fdf8c-115">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="fdf8c-116">Weitere Informationen zur Vorgehensweise beim Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="fdf8c-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdf8c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fdf8c-117">Child Elements</span></span>  
  
|<span data-ttu-id="fdf8c-118">Element</span><span class="sxs-lookup"><span data-stu-id="fdf8c-118">Element</span></span>|<span data-ttu-id="fdf8c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdf8c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdf8c-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="fdf8c-120">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="fdf8c-121">Wenn die `type` Attribut gibt an, der konfigurationsbasierten ausstellernamenregistrierung (die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse), wird die [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="fdf8c-122">Die [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element dauert `<add>`, `<clear>`, oder `<remove>` -Elemente als untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-122">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fdf8c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fdf8c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fdf8c-124">Element</span><span class="sxs-lookup"><span data-stu-id="fdf8c-124">Element</span></span>|<span data-ttu-id="fdf8c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdf8c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdf8c-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="fdf8c-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="fdf8c-127">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdf8c-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdf8c-128">Remarks</span></span>  
 <span data-ttu-id="fdf8c-129">Alle ausstellertoken werden überprüft, eine Ausstellernamen-Registrierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="fdf8c-130">Dies ist ein Objekt, das von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="fdf8c-131">Die Ausstellernamen-Registrierung wird verwendet, um einen merknamen kryptografischen Informationen zuzuordnen, die benötigt werden, um zu überprüfen, ob die Signaturen von Token, die vom entsprechenden Aussteller erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="fdf8c-132">Die Ausstellernamen-Registrierung verwaltet eine Liste der Zertifikataussteller, die die Anwendung der vertrauenden Seite (Relying Party, RP) vertraut.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="fdf8c-133">Der Typ, der die Ausstellernamen-Registrierung angegeben ist, mit der `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="fdf8c-134">Die `<issuerNameRegistry>` -Element kann eine oder mehrere untergeordnete Elemente, die Konfiguration für den angegebenen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="fdf8c-135">Geben Sie die Logik, die verarbeitet diese untergeordneten Elemente durch Überschreiben der <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="fdf8c-136">WIF stellt einen einzelnen Aussteller namens Registrierungstyp standardmäßig die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="fdf8c-137">Diese Klasse verwendet eine Reihe von Zertifikaten vertrauenswürdiger Aussteller, die in der Konfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="fdf8c-138">Es muss ein untergeordnetes Konfigurationselement `<trustedIssuers>`, unter dem die Auflistung von Zertifikaten vertrauenswürdiger Aussteller konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="fdf8c-139">Vertrauenswürdige Zertifikate angegeben sind, mit der ASN. 1-codierte Form des Zertifikatfingerabdrucks und hinzugefügt oder aus der Auflistung entfernt werden, mithilfe von `<add>`, `<clear>`, oder `<remove>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="fdf8c-140">Die `<issuerNameRegistry>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdf8c-141">Angeben der `<issuerNameRegistry>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="fdf8c-142">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf8c-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdf8c-143">Example</span></span>  
 <span data-ttu-id="fdf8c-144">Das folgende XML zeigt, wie an den Aussteller für die Konfiguration basiert-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="fdf8c-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdf8c-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdf8c-145">See also</span></span>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
