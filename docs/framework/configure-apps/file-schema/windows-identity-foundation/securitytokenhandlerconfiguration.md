---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152566"
---
# \<securityTokenHandlerConfiguration>
<span data-ttu-id="97ce5-101">Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="97ce5-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="97ce5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="97ce5-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97ce5-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="97ce5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="97ce5-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="97ce5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97ce5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="97ce5-105">Attributes</span></span>  
  
|<span data-ttu-id="97ce5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="97ce5-106">Attribute</span></span>|<span data-ttu-id="97ce5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97ce5-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97ce5-108">savebootstrapcontext</span><span class="sxs-lookup"><span data-stu-id="97ce5-108">saveBootstrapContext</span></span>|<span data-ttu-id="97ce5-109">Gibt an, ob Bootstrap-Token in das Sitzungs Token eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="97ce5-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="97ce5-110">Der Wert kann auch für eine tokenhandlerauflistung festgelegt werden, indem das- `saveBootstrapContext` Attribut für das-Element festgelegt wird [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="97ce5-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="97ce5-111">Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="97ce5-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="97ce5-112">maximumclockschiefe</span><span class="sxs-lookup"><span data-stu-id="97ce5-112">maximumClockSkew</span></span>|<span data-ttu-id="97ce5-113">Eine <xref:System.TimeSpan> , die die maximal zulässige Takt Neigung angibt.</span><span class="sxs-lookup"><span data-stu-id="97ce5-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="97ce5-114">Steuert die maximal zulässige Takt Neigung, wenn Zeit empfindliche Vorgänge durchgeführt werden, z. b. das Überprüfen der Ablaufzeit einer Anmelde Sitzung.</span><span class="sxs-lookup"><span data-stu-id="97ce5-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="97ce5-115">Der Standardwert ist 5 Minuten, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="97ce5-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="97ce5-116">Weitere Informationen zum Angeben von <xref:System.TimeSpan> Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="97ce5-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="97ce5-117">Die maximale Takt Abweichung kann auch auf Dienst Ebene festgelegt werden, indem das- `maximumClockSkew` Attribut für das-Element festgelegt wird [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="97ce5-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="97ce5-118">Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="97ce5-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97ce5-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97ce5-119">Child Elements</span></span>  
  
|<span data-ttu-id="97ce5-120">Element</span><span class="sxs-lookup"><span data-stu-id="97ce5-120">Element</span></span>|<span data-ttu-id="97ce5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97ce5-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="97ce5-122">Gibt den Satz von URIs an, die akzeptable Bezeichner dieser vertrauenden Seite sind.</span><span class="sxs-lookup"><span data-stu-id="97ce5-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="97ce5-123">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="97ce5-124">Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97ce5-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="97ce5-125">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97ce5-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="97ce5-126">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="97ce5-127">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97ce5-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="97ce5-128">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97ce5-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="97ce5-129">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="97ce5-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="97ce5-130">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="97ce5-131">Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97ce5-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="97ce5-132">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="97ce5-133">Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97ce5-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="97ce5-134">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="97ce5-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="97ce5-135">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="97ce5-136">Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97ce5-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="97ce5-137">Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="97ce5-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="97ce5-138">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="97ce5-139">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="97ce5-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="97ce5-140">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97ce5-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="97ce5-141">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97ce5-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97ce5-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97ce5-142">Parent Elements</span></span>  
  
|<span data-ttu-id="97ce5-143">Element</span><span class="sxs-lookup"><span data-stu-id="97ce5-143">Element</span></span>|<span data-ttu-id="97ce5-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97ce5-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="97ce5-145">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="97ce5-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97ce5-146">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="97ce5-146">Remarks</span></span>  
 <span data-ttu-id="97ce5-147">In diesem Abschnitt werden Eigenschaftswerte für ein-Objekt bereitstellt <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="97ce5-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="97ce5-148">Die in diesem Abschnitt konfigurierten Einstellungen überschreiben die für den Dienst konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="97ce5-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="97ce5-149">Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben werden, die beim Hinzufügen eines Handlers zur Auflistung der Sicherheitstokenhandler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97ce5-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97ce5-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97ce5-150">Example</span></span>  
  
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
