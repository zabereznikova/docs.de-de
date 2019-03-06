---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360406"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="9d1e7-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="9d1e7-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="9d1e7-102">Ermöglicht die Konfiguration für die Sammlung von tokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="9d1e7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9d1e7-103">\<system.identityModel></span></span>  
<span data-ttu-id="9d1e7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9d1e7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="9d1e7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="9d1e7-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="9d1e7-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="9d1e7-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d1e7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d1e7-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d1e7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1e7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9d1e7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d1e7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d1e7-110">Attributes</span></span>  
  
|<span data-ttu-id="9d1e7-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="9d1e7-111">Attribute</span></span>|<span data-ttu-id="9d1e7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1e7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d1e7-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="9d1e7-113">saveBootstrapContext</span></span>|<span data-ttu-id="9d1e7-114">Gibt an, ob bootstrap-Token in das Sitzungstoken, das enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="9d1e7-115">Der Wert kann auch auf eine Auflistung der Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut für die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="9d1e7-116">Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="9d1e7-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="9d1e7-117">maximumClockSkew</span></span>|<span data-ttu-id="9d1e7-118">Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="9d1e7-119">Steuert die maximal erlaubte uhrabweichung, beim Durchführen von zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine Anmeldung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="9d1e7-120">Der Standardwert ist 5 Minuten, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="9d1e7-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="9d1e7-121">Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9d1e7-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="9d1e7-122">Die maximale uhrabweichung kann auch auf Dienstebene festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut für die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="9d1e7-123">Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d1e7-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1e7-124">Child Elements</span></span>  
  
|<span data-ttu-id="9d1e7-125">Element</span><span class="sxs-lookup"><span data-stu-id="9d1e7-125">Element</span></span>|<span data-ttu-id="9d1e7-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1e7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d1e7-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="9d1e7-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="9d1e7-128">Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden sind.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="9d1e7-129">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-129">Optional.</span></span>|  
|[<span data-ttu-id="9d1e7-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="9d1e7-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="9d1e7-131">Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="9d1e7-132">Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9d1e7-133">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-133">Optional.</span></span>|  
|[<span data-ttu-id="9d1e7-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="9d1e7-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="9d1e7-135">Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="9d1e7-136">Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9d1e7-137">Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="9d1e7-138">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-138">Optional.</span></span>|  
|[<span data-ttu-id="9d1e7-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="9d1e7-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="9d1e7-140">Konfiguriert die Ausstellernamen-Registrierung, die von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9d1e7-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-141">Optional.</span></span>|  
|[<span data-ttu-id="9d1e7-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="9d1e7-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="9d1e7-143">Registriert die Aussteller-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9d1e7-144">Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="9d1e7-145">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-145">Optional.</span></span>|  
|[<span data-ttu-id="9d1e7-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="9d1e7-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="9d1e7-147">Registriert die Service-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9d1e7-148">Dienst-tokenresolvers wird verwendet, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="9d1e7-149">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-149">Optional.</span></span>|  
|[<span data-ttu-id="9d1e7-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="9d1e7-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="9d1e7-151">Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="9d1e7-152">Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="9d1e7-153">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d1e7-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d1e7-154">Parent Elements</span></span>  
  
|<span data-ttu-id="9d1e7-155">Element</span><span class="sxs-lookup"><span data-stu-id="9d1e7-155">Element</span></span>|<span data-ttu-id="9d1e7-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1e7-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d1e7-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="9d1e7-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="9d1e7-158">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d1e7-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d1e7-159">Remarks</span></span>  
 <span data-ttu-id="9d1e7-160">Dieser Abschnitt enthält die Eigenschaftswerte für eine <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="9d1e7-161">In diesem Abschnitt konfigurierten Einstellungen außer Kraft setzen, die auf den Dienst konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="9d1e7-162">Einige dieser Einstellungen können wiederum von Einstellungen überschrieben werden, die angegeben werden, wenn das Sicherheitstoken-Handlerauflistung ein Handler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9d1e7-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d1e7-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d1e7-163">Example</span></span>  
  
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
