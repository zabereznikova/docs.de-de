---
title: <transport> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732815"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="13865-102">\<transport> von \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="13865-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="13865-103">Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.</span><span class="sxs-lookup"><span data-stu-id="13865-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="13865-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13865-104">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13865-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="13865-105">Attributes and Elements</span></span>  
 <span data-ttu-id="13865-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13865-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13865-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="13865-107">Attributes</span></span>  
  
|<span data-ttu-id="13865-108">attribute</span><span class="sxs-lookup"><span data-stu-id="13865-108">Attribute</span></span>|<span data-ttu-id="13865-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13865-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13865-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="13865-110">clientCredentialType</span></span>|<span data-ttu-id="13865-111">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung mithilfe der HTTP-Authentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13865-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="13865-112">Der Standardwert lautet `None`.</span><span class="sxs-lookup"><span data-stu-id="13865-112">The default is `None`.</span></span> <span data-ttu-id="13865-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="13865-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="13865-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="13865-114">proxyCredentialType</span></span>|<span data-ttu-id="13865-115">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung innerhalb einer Domäne mithilfe eines Proxys über HTTP verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13865-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="13865-116">Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet.</span><span class="sxs-lookup"><span data-stu-id="13865-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="13865-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="13865-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="13865-118">realm</span><span class="sxs-lookup"><span data-stu-id="13865-118">realm</span></span>|<span data-ttu-id="13865-119">Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="13865-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="13865-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="13865-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="13865-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="13865-121">policyEnforcement</span></span>|<span data-ttu-id="13865-122">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="13865-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="13865-123">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="13865-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="13865-124">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13865-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="13865-125">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="13865-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="13865-126">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="13865-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="13865-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="13865-127">protectionScenario</span></span>|<span data-ttu-id="13865-128">Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.</span><span class="sxs-lookup"><span data-stu-id="13865-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="13865-129">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="13865-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="13865-130">Wert</span><span class="sxs-lookup"><span data-stu-id="13865-130">Value</span></span>|<span data-ttu-id="13865-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13865-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="13865-132">Keine</span><span class="sxs-lookup"><span data-stu-id="13865-132">None</span></span>|<span data-ttu-id="13865-133">Nachrichten werden nicht während der Übertragung gesichert.</span><span class="sxs-lookup"><span data-stu-id="13865-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="13865-134">Basic</span><span class="sxs-lookup"><span data-stu-id="13865-134">Basic</span></span>|<span data-ttu-id="13865-135">Gibt die Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="13865-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="13865-136">Digest</span><span class="sxs-lookup"><span data-stu-id="13865-136">Digest</span></span>|<span data-ttu-id="13865-137">Gibt die Digestauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="13865-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="13865-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="13865-138">Ntlm</span></span>|<span data-ttu-id="13865-139">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="13865-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="13865-140">Windows</span><span class="sxs-lookup"><span data-stu-id="13865-140">Windows</span></span>|<span data-ttu-id="13865-141">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="13865-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="13865-142">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="13865-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="13865-143">Wert</span><span class="sxs-lookup"><span data-stu-id="13865-143">Value</span></span>|<span data-ttu-id="13865-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13865-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="13865-145">Keine</span><span class="sxs-lookup"><span data-stu-id="13865-145">None</span></span>|<span data-ttu-id="13865-146">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="13865-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="13865-147">Basic</span><span class="sxs-lookup"><span data-stu-id="13865-147">Basic</span></span>|<span data-ttu-id="13865-148">Gibt die Standardauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="13865-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="13865-149">Digest</span><span class="sxs-lookup"><span data-stu-id="13865-149">Digest</span></span>|<span data-ttu-id="13865-150">Gibt die Digestauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="13865-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="13865-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="13865-151">Ntlm</span></span>|<span data-ttu-id="13865-152">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="13865-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="13865-153">Windows</span><span class="sxs-lookup"><span data-stu-id="13865-153">Windows</span></span>|<span data-ttu-id="13865-154">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="13865-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="13865-155">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="13865-155">Certificate</span></span>|<span data-ttu-id="13865-156">Führt die Clientauthentifizierung mit einem Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="13865-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="13865-157">Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="13865-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13865-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13865-158">Child Elements</span></span>  
 <span data-ttu-id="13865-159">Keine</span><span class="sxs-lookup"><span data-stu-id="13865-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13865-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13865-160">Parent Elements</span></span>  
  
|<span data-ttu-id="13865-161">Element</span><span class="sxs-lookup"><span data-stu-id="13865-161">Element</span></span>|<span data-ttu-id="13865-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13865-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="13865-163">Definiert die Sicherheitsfunktionen für [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="13865-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="13865-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13865-164">Example</span></span>  
 <span data-ttu-id="13865-165">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="13865-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="13865-166">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="13865-166">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="13865-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13865-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="13865-168">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="13865-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="13865-169">Bindungen</span><span class="sxs-lookup"><span data-stu-id="13865-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="13865-170">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="13865-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="13865-171">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="13865-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
