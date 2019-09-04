---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251889"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="02b09-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="02b09-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="02b09-102">Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="02b09-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="02b09-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02b09-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02b09-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="02b09-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="02b09-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="02b09-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="02b09-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="02b09-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="02b09-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securitytokenhandlerconfiguration->**</span><span class="sxs-lookup"><span data-stu-id="02b09-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b09-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="02b09-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02b09-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02b09-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02b09-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02b09-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02b09-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="02b09-111">Attributes</span></span>  
  
|<span data-ttu-id="02b09-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="02b09-112">Attribute</span></span>|<span data-ttu-id="02b09-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02b09-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02b09-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="02b09-114">saveBootstrapContext</span></span>|<span data-ttu-id="02b09-115">Gibt an, ob Bootstrap-Token in das Sitzungs Token eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="02b09-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="02b09-116">Der Wert kann auch für eine tokenhandlerauflistung festgelegt werden `saveBootstrapContext` , indem das-Attribut für das [ \<identityconfiguration->](identityconfiguration.md) Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="02b09-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="02b09-117">Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="02b09-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="02b09-118">maximumclockschiefe</span><span class="sxs-lookup"><span data-stu-id="02b09-118">maximumClockSkew</span></span>|<span data-ttu-id="02b09-119">Eine <xref:System.TimeSpan> , die die maximal zulässige Takt Neigung angibt.</span><span class="sxs-lookup"><span data-stu-id="02b09-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="02b09-120">Steuert die maximal zulässige Takt Neigung, wenn Zeit empfindliche Vorgänge durchgeführt werden, z. b. das Überprüfen der Ablaufzeit einer Anmelde Sitzung.</span><span class="sxs-lookup"><span data-stu-id="02b09-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="02b09-121">Der Standardwert ist 5 Minuten, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="02b09-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="02b09-122">Weitere Informationen zum angeben <xref:System.TimeSpan> von Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="02b09-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="02b09-123">Die maximale Takt Abweichung kann auch auf Dienst Ebene festgelegt werden, indem das `maximumClockSkew` -Attribut für das [ \<identityconfiguration->](identityconfiguration.md) Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="02b09-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="02b09-124">Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="02b09-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02b09-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02b09-125">Child Elements</span></span>  
  
|<span data-ttu-id="02b09-126">Element</span><span class="sxs-lookup"><span data-stu-id="02b09-126">Element</span></span>|<span data-ttu-id="02b09-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02b09-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02b09-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="02b09-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="02b09-129">Gibt den Satz von URIs an, die akzeptable Bezeichner dieser vertrauenden Seite sind.</span><span class="sxs-lookup"><span data-stu-id="02b09-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="02b09-130">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-130">Optional.</span></span>|  
|[<span data-ttu-id="02b09-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="02b09-131">\<caches></span></span>](caches.md)|<span data-ttu-id="02b09-132">Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02b09-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="02b09-133">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02b09-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="02b09-134">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-134">Optional.</span></span>|  
|[<span data-ttu-id="02b09-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="02b09-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="02b09-136">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02b09-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="02b09-137">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02b09-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="02b09-138">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="02b09-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="02b09-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-139">Optional.</span></span>|  
|[<span data-ttu-id="02b09-140">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="02b09-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="02b09-141">Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02b09-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="02b09-142">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-142">Optional.</span></span>|  
|[<span data-ttu-id="02b09-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="02b09-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="02b09-144">Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02b09-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="02b09-145">Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="02b09-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="02b09-146">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-146">Optional.</span></span>|  
|[<span data-ttu-id="02b09-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="02b09-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="02b09-148">Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02b09-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="02b09-149">Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="02b09-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="02b09-150">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-150">Optional.</span></span>|  
|[<span data-ttu-id="02b09-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="02b09-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="02b09-152">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="02b09-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="02b09-153">Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02b09-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="02b09-154">Optional.</span><span class="sxs-lookup"><span data-stu-id="02b09-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02b09-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02b09-155">Parent Elements</span></span>  
  
|<span data-ttu-id="02b09-156">Element</span><span class="sxs-lookup"><span data-stu-id="02b09-156">Element</span></span>|<span data-ttu-id="02b09-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02b09-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02b09-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="02b09-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="02b09-159">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="02b09-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02b09-160">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02b09-160">Remarks</span></span>  
 <span data-ttu-id="02b09-161">In diesem Abschnitt werden Eigenschaftswerte <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> für ein-Objekt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="02b09-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="02b09-162">Die in diesem Abschnitt konfigurierten Einstellungen überschreiben die für den Dienst konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="02b09-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="02b09-163">Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben werden, die beim Hinzufügen eines Handlers zur Auflistung der Sicherheitstokenhandler angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02b09-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b09-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02b09-164">Example</span></span>  
  
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
