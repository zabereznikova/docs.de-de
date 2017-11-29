---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: be98c93452c9c7a37ecad5b03f5160ea08f2c82e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="19341-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="19341-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="19341-103">Die Konfiguration für die Auflistung der Tokenhandler bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="19341-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="19341-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="19341-104">\<system.identityModel></span></span>  
<span data-ttu-id="19341-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="19341-105">\<identityConfiguration></span></span>  
<span data-ttu-id="19341-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="19341-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="19341-107">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="19341-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19341-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="19341-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19341-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="19341-109">Attributes and Elements</span></span>  
 <span data-ttu-id="19341-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="19341-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19341-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="19341-111">Attributes</span></span>  
  
|<span data-ttu-id="19341-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="19341-112">Attribute</span></span>|<span data-ttu-id="19341-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19341-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19341-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="19341-114">saveBootstrapContext</span></span>|<span data-ttu-id="19341-115">Gibt an, ob bootstrap-Token in das Sitzungstoken aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="19341-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="19341-116">Der Wert kann auch auf eine Auflistung Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut auf die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="19341-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="19341-117">Ein Wert festgelegt, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="19341-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="19341-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="19341-118">maximumClockSkew</span></span>|<span data-ttu-id="19341-119">Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt.</span><span class="sxs-lookup"><span data-stu-id="19341-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="19341-120">Die maximal erlaubte taktverschiebung steuert die Ausführung zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine anmeldesitzung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="19341-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="19341-121">Der Standardwert beträgt 5 Minuten "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="19341-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="19341-122">Weitere Informationen zum Angeben der <xref:System.TimeSpan> -Werte finden Sie in [Timespan Werte](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="19341-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="19341-123">Die maximale taktverschiebung kann auch auf Dienstebene festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut auf die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="19341-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="19341-124">Ein Wert festgelegt, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="19341-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19341-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19341-125">Child Elements</span></span>  
  
|<span data-ttu-id="19341-126">Element</span><span class="sxs-lookup"><span data-stu-id="19341-126">Element</span></span>|<span data-ttu-id="19341-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19341-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19341-128">\<AudienceUris ></span><span class="sxs-lookup"><span data-stu-id="19341-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="19341-129">Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden sind.</span><span class="sxs-lookup"><span data-stu-id="19341-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="19341-130">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-130">Optional.</span></span>|  
|[<span data-ttu-id="19341-131">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="19341-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="19341-132">Registriert die Caches für die Sitzungstoken und token-Replay-Erkennung verwendet.</span><span class="sxs-lookup"><span data-stu-id="19341-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="19341-133">Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19341-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="19341-134">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-134">Optional.</span></span>|  
|[<span data-ttu-id="19341-135">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="19341-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="19341-136">Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="19341-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="19341-137">Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19341-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="19341-138">Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="19341-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="19341-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-139">Optional.</span></span>|  
|[<span data-ttu-id="19341-140">\<IssuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="19341-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="19341-141">Konfiguriert die ausstellernamenregistration, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19341-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="19341-142">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-142">Optional.</span></span>|  
|[<span data-ttu-id="19341-143">\<IssuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="19341-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="19341-144">Registriert die Aussteller-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19341-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="19341-145">Die Aussteller-tokenresolver wird zum Auflösen von der signiertokens für eingehende Token und Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="19341-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="19341-146">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-146">Optional.</span></span>|  
|[<span data-ttu-id="19341-147">\<ServiceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="19341-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="19341-148">Registriert die Dienst-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19341-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="19341-149">Die Dienst-tokenresolver dient zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="19341-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="19341-150">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-150">Optional.</span></span>|  
|[<span data-ttu-id="19341-151">\<TokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="19341-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="19341-152">Tokenwiedergabeerkennung aktiviert, und gibt die Ablaufzeit für Token.</span><span class="sxs-lookup"><span data-stu-id="19341-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="19341-153">Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19341-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="19341-154">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="19341-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19341-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19341-155">Parent Elements</span></span>  
  
|<span data-ttu-id="19341-156">Element</span><span class="sxs-lookup"><span data-stu-id="19341-156">Element</span></span>|<span data-ttu-id="19341-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19341-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19341-158">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="19341-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="19341-159">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="19341-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19341-160">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19341-160">Remarks</span></span>  
 <span data-ttu-id="19341-161">Dieser Abschnitt enthält die Eigenschaftenwerte für eine <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt.</span><span class="sxs-lookup"><span data-stu-id="19341-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="19341-162">In diesem Abschnitt konfigurierten Einstellungen außer Kraft für den Dienst konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="19341-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="19341-163">Einige dieser Einstellungen können wiederum von Einstellungen überschrieben werden, die angegeben werden, wenn die Sicherheit Tokenhandler-Auflistung ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="19341-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19341-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19341-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
