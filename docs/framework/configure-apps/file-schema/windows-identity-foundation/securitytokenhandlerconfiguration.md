---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152566"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="e3192-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="e3192-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="e3192-102">Stellt die Konfiguration für die Auflistung von Tokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="e3192-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="e3192-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e3192-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e3192-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e3192-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e3192-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e3192-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e3192-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e3192-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e3192-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="e3192-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3192-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3192-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3192-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e3192-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3192-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3192-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3192-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="e3192-111">Attributes</span></span>  
  
|<span data-ttu-id="e3192-112">attribute</span><span class="sxs-lookup"><span data-stu-id="e3192-112">Attribute</span></span>|<span data-ttu-id="e3192-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3192-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3192-114">SaveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="e3192-114">saveBootstrapContext</span></span>|<span data-ttu-id="e3192-115">Gibt an, ob Bootstrap-Token in das Sitzungstoken eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3192-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="e3192-116">Der Wert kann auch für eine Tokenhandlerauflistung festgelegt werden, indem das `saveBootstrapContext` Attribut für das [ \<identityConfiguration>-Element](identityconfiguration.md) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e3192-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="e3192-117">Ein wertfürst, der für die Tokenhandlerauflistung festgelegt ist, überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="e3192-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="e3192-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="e3192-118">maximumClockSkew</span></span>|<span data-ttu-id="e3192-119">A, <xref:System.TimeSpan> das die maximal zulässige Taktschiefe angibt.</span><span class="sxs-lookup"><span data-stu-id="e3192-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="e3192-120">Steuert die maximal zulässige Taktneigung beim Ausführen zeitabhängiger Vorgänge, z. B. das Überprüfen der Ablaufzeit einer Anmeldesitzung.</span><span class="sxs-lookup"><span data-stu-id="e3192-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="e3192-121">Der Standardwert ist 5 Minuten, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="e3192-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="e3192-122">Weitere Informationen zum Angeben <xref:System.TimeSpan> von Werten finden Sie unter [Zeitspannenwerte](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="e3192-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="e3192-123">Die maximale Taktneigung kann auch auf Serviceebene `maximumClockSkew` festgelegt werden, indem das Attribut für das [ \<identityConfiguration>-Element](identityconfiguration.md) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e3192-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="e3192-124">Ein wertfürst, der für die Tokenhandlerauflistung festgelegt ist, überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="e3192-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3192-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3192-125">Child Elements</span></span>  
  
|<span data-ttu-id="e3192-126">Element</span><span class="sxs-lookup"><span data-stu-id="e3192-126">Element</span></span>|<span data-ttu-id="e3192-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3192-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3192-128">\<PublikumUris></span><span class="sxs-lookup"><span data-stu-id="e3192-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="e3192-129">Gibt den Satz von URIs an, die akzeptable Bezeichner dieser vertrauenden Partei sind.</span><span class="sxs-lookup"><span data-stu-id="e3192-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="e3192-130">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-130">Optional.</span></span>|  
|[<span data-ttu-id="e3192-131">\<Caches></span><span class="sxs-lookup"><span data-stu-id="e3192-131">\<caches></span></span>](caches.md)|<span data-ttu-id="e3192-132">Registriert die Caches, die für Sitzungstoken und Token-Wiedergabeerkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3192-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="e3192-133">Kann auf Serviceebene oder in einer Sicherheitstokenhandlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3192-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e3192-134">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-134">Optional.</span></span>|  
|[<span data-ttu-id="e3192-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="e3192-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="e3192-136">Steuert die Einstellungen, die Tokenhandler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3192-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="e3192-137">Kann auf Serviceebene oder in einer Sicherheitstokenhandlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3192-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e3192-138">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validator konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e3192-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="e3192-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-139">Optional.</span></span>|  
|[<span data-ttu-id="e3192-140">\<IssuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="e3192-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="e3192-141">Konfiguriert die Ausstellernamenregistrierung, die von Handlern in der Tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3192-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e3192-142">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-142">Optional.</span></span>|  
|[<span data-ttu-id="e3192-143">\<IssuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="e3192-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="e3192-144">Registriert den Ausstellertokenlöser, der von Handlern in der Tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3192-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e3192-145">Der Ausstellertokenlöser wird verwendet, um das Signaturtoken für eingehende Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e3192-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e3192-146">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-146">Optional.</span></span>|  
|[<span data-ttu-id="e3192-147">\<dienstTokenResolver></span><span class="sxs-lookup"><span data-stu-id="e3192-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="e3192-148">Registriert den Diensttoken-Resolver, der von Handlern in der Tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3192-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e3192-149">Der Diensttokenlöser wird verwendet, um das Verschlüsselungstoken für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="e3192-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="e3192-150">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-150">Optional.</span></span>|  
|[<span data-ttu-id="e3192-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="e3192-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="e3192-152">Aktiviert die Token-Wiedergabeerkennung und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="e3192-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="e3192-153">Kann auf Serviceebene oder in einer Sicherheitstokenhandlerauflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3192-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e3192-154">Optional.</span><span class="sxs-lookup"><span data-stu-id="e3192-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3192-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e3192-155">Parent Elements</span></span>  
  
|<span data-ttu-id="e3192-156">Element</span><span class="sxs-lookup"><span data-stu-id="e3192-156">Element</span></span>|<span data-ttu-id="e3192-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3192-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3192-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e3192-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="e3192-159">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="e3192-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3192-160">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e3192-160">Remarks</span></span>  
 <span data-ttu-id="e3192-161">Dieser Abschnitt stellt Eigenschaftswerte für ein <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt bereit.</span><span class="sxs-lookup"><span data-stu-id="e3192-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="e3192-162">Die in diesem Abschnitt konfigurierten Einstellungen überschreiben die für den Dienst konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e3192-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="e3192-163">Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben werden, die angegeben werden, wenn ein Handler zur Sicherheitstokenhandlerauflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e3192-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3192-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3192-164">Example</span></span>  
  
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
