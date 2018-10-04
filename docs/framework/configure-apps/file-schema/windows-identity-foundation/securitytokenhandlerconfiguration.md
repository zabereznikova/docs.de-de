---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793278"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="4f147-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="4f147-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="4f147-103">Ermöglicht die Konfiguration für die Sammlung von tokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="4f147-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="4f147-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4f147-104">\<system.identityModel></span></span>  
<span data-ttu-id="4f147-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4f147-105">\<identityConfiguration></span></span>  
<span data-ttu-id="4f147-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="4f147-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4f147-107">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="4f147-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f147-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f147-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f147-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f147-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4f147-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f147-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f147-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f147-111">Attributes</span></span>  
  
|<span data-ttu-id="4f147-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4f147-112">Attribute</span></span>|<span data-ttu-id="4f147-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f147-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f147-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="4f147-114">saveBootstrapContext</span></span>|<span data-ttu-id="4f147-115">Gibt an, ob bootstrap-Token in das Sitzungstoken, das enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="4f147-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="4f147-116">Der Wert kann auch auf eine Auflistung der Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut für die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="4f147-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="4f147-117">Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4f147-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="4f147-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="4f147-118">maximumClockSkew</span></span>|<span data-ttu-id="4f147-119">Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt.</span><span class="sxs-lookup"><span data-stu-id="4f147-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="4f147-120">Steuert die maximal erlaubte uhrabweichung, beim Durchführen von zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine Anmeldung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4f147-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="4f147-121">Der Standardwert ist 5 Minuten, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="4f147-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="4f147-122">Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f147-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="4f147-123">Die maximale uhrabweichung kann auch auf Dienstebene festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut für die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="4f147-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="4f147-124">Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4f147-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f147-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f147-125">Child Elements</span></span>  
  
|<span data-ttu-id="4f147-126">Element</span><span class="sxs-lookup"><span data-stu-id="4f147-126">Element</span></span>|<span data-ttu-id="4f147-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f147-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f147-128">\<AudienceUris ></span><span class="sxs-lookup"><span data-stu-id="4f147-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="4f147-129">Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden sind.</span><span class="sxs-lookup"><span data-stu-id="4f147-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="4f147-130">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-130">Optional.</span></span>|  
|[<span data-ttu-id="4f147-131">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="4f147-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="4f147-132">Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f147-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="4f147-133">Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f147-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="4f147-134">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-134">Optional.</span></span>|  
|[<span data-ttu-id="4f147-135">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="4f147-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="4f147-136">Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f147-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="4f147-137">Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f147-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="4f147-138">Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4f147-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="4f147-139">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-139">Optional.</span></span>|  
|[<span data-ttu-id="4f147-140">\<"issuerNameRegistry" ></span><span class="sxs-lookup"><span data-stu-id="4f147-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="4f147-141">Konfiguriert die Ausstellernamen-Registrierung, die von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f147-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="4f147-142">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-142">Optional.</span></span>|  
|[<span data-ttu-id="4f147-143">\<IssuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="4f147-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="4f147-144">Registriert die Aussteller-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f147-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="4f147-145">Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="4f147-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="4f147-146">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-146">Optional.</span></span>|  
|[<span data-ttu-id="4f147-147">\<ServiceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="4f147-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="4f147-148">Registriert die Service-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f147-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="4f147-149">Dienst-tokenresolvers wird verwendet, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4f147-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="4f147-150">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-150">Optional.</span></span>|  
|[<span data-ttu-id="4f147-151">\<TokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="4f147-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="4f147-152">Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token.</span><span class="sxs-lookup"><span data-stu-id="4f147-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="4f147-153">Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f147-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="4f147-154">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4f147-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f147-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f147-155">Parent Elements</span></span>  
  
|<span data-ttu-id="4f147-156">Element</span><span class="sxs-lookup"><span data-stu-id="4f147-156">Element</span></span>|<span data-ttu-id="4f147-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f147-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f147-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4f147-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="4f147-159">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="4f147-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f147-160">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f147-160">Remarks</span></span>  
 <span data-ttu-id="4f147-161">Dieser Abschnitt enthält die Eigenschaftswerte für eine <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4f147-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="4f147-162">In diesem Abschnitt konfigurierten Einstellungen außer Kraft setzen, die auf den Dienst konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4f147-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="4f147-163">Einige dieser Einstellungen können wiederum von Einstellungen überschrieben werden, die angegeben werden, wenn das Sicherheitstoken-Handlerauflistung ein Handler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4f147-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f147-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f147-164">Example</span></span>  
  
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
