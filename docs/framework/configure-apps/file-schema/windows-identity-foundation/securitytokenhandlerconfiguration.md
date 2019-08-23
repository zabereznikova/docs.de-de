---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 0aefaa808dfc32085a208420fcd582b1671acc64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942448"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="a7a3b-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="a7a3b-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="a7a3b-102">Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="a7a3b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a7a3b-103">\<system.identityModel></span></span>  
<span data-ttu-id="a7a3b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a7a3b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a7a3b-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a7a3b-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a7a3b-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="a7a3b-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a3b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7a3b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7a3b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7a3b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a7a3b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7a3b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7a3b-110">Attributes</span></span>  
  
|<span data-ttu-id="a7a3b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a7a3b-111">Attribute</span></span>|<span data-ttu-id="a7a3b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7a3b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7a3b-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="a7a3b-113">saveBootstrapContext</span></span>|<span data-ttu-id="a7a3b-114">Gibt an, ob Bootstrap-Token in das Sitzungs Token eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="a7a3b-115">Der Wert kann auch für eine tokenhandlerauflistung festgelegt werden `saveBootstrapContext` , indem das-Attribut für das [ \<identityconfiguration->](identityconfiguration.md) Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="a7a3b-116">Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="a7a3b-117">maximumclockschiefe</span><span class="sxs-lookup"><span data-stu-id="a7a3b-117">maximumClockSkew</span></span>|<span data-ttu-id="a7a3b-118">Eine <xref:System.TimeSpan> , die die maximal zulässige Takt Neigung angibt.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="a7a3b-119">Steuert die maximal zulässige Takt Neigung, wenn Zeit empfindliche Vorgänge durchgeführt werden, z. b. das Überprüfen der Ablaufzeit einer Anmelde Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="a7a3b-120">Der Standardwert ist 5 Minuten, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="a7a3b-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="a7a3b-121">Weitere Informationen zum angeben <xref:System.TimeSpan> von Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="a7a3b-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="a7a3b-122">Die maximale Takt Abweichung kann auch auf Dienst Ebene festgelegt werden, indem das `maximumClockSkew` -Attribut für das [ \<identityconfiguration->](identityconfiguration.md) Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="a7a3b-123">Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7a3b-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7a3b-124">Child Elements</span></span>  
  
|<span data-ttu-id="a7a3b-125">Element</span><span class="sxs-lookup"><span data-stu-id="a7a3b-125">Element</span></span>|<span data-ttu-id="a7a3b-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7a3b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7a3b-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="a7a3b-127">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="a7a3b-128">Gibt den Satz von URIs an, die akzeptable Bezeichner dieser vertrauenden Seite sind.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="a7a3b-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-129">Optional.</span></span>|  
|[<span data-ttu-id="a7a3b-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="a7a3b-130">\<caches></span></span>](caches.md)|<span data-ttu-id="a7a3b-131">Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="a7a3b-132">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="a7a3b-133">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-133">Optional.</span></span>|  
|[<span data-ttu-id="a7a3b-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="a7a3b-134">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="a7a3b-135">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="a7a3b-136">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="a7a3b-137">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="a7a3b-138">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-138">Optional.</span></span>|  
|[<span data-ttu-id="a7a3b-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="a7a3b-139">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="a7a3b-140">Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a7a3b-141">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-141">Optional.</span></span>|  
|[<span data-ttu-id="a7a3b-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="a7a3b-142">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="a7a3b-143">Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a7a3b-144">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="a7a3b-145">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-145">Optional.</span></span>|  
|[<span data-ttu-id="a7a3b-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="a7a3b-146">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="a7a3b-147">Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a7a3b-148">Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="a7a3b-149">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-149">Optional.</span></span>|  
|[<span data-ttu-id="a7a3b-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="a7a3b-150">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="a7a3b-151">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="a7a3b-152">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="a7a3b-153">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7a3b-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7a3b-154">Parent Elements</span></span>  
  
|<span data-ttu-id="a7a3b-155">Element</span><span class="sxs-lookup"><span data-stu-id="a7a3b-155">Element</span></span>|<span data-ttu-id="a7a3b-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7a3b-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7a3b-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a7a3b-157">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="a7a3b-158">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7a3b-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7a3b-159">Remarks</span></span>  
 <span data-ttu-id="a7a3b-160">In diesem Abschnitt werden Eigenschaftswerte <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> für ein-Objekt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="a7a3b-161">Die in diesem Abschnitt konfigurierten Einstellungen überschreiben die für den Dienst konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="a7a3b-162">Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben werden, die beim Hinzufügen eines Handlers zur Auflistung der Sicherheitstokenhandler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7a3b-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7a3b-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7a3b-163">Example</span></span>  
  
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
