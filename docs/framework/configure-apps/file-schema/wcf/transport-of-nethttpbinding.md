---
title: <transport> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: f9f784329081f6a18560991378a4527c731f4d31
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934711"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="4f992-102">\<Transport > von \<"netthttpbinding" ></span><span class="sxs-lookup"><span data-stu-id="4f992-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="4f992-103">Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.</span><span class="sxs-lookup"><span data-stu-id="4f992-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="4f992-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f992-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4f992-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4f992-105">\<bindings></span></span>  
<span data-ttu-id="4f992-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4f992-106">\<netHttpBinding></span></span>  
<span data-ttu-id="4f992-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f992-107">\<binding></span></span>  
<span data-ttu-id="4f992-108">\<security></span><span class="sxs-lookup"><span data-stu-id="4f992-108">\<security></span></span>  
<span data-ttu-id="4f992-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="4f992-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f992-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f992-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f992-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f992-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f992-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f992-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f992-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f992-113">Attributes</span></span>  
  
|<span data-ttu-id="4f992-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="4f992-114">Attribute</span></span>|<span data-ttu-id="4f992-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f992-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f992-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="4f992-116">clientCredentialType</span></span>|<span data-ttu-id="4f992-117">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung mithilfe der HTTP-Authentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4f992-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="4f992-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="4f992-118">The default is `None`.</span></span> <span data-ttu-id="4f992-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="4f992-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="4f992-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="4f992-120">proxyCredentialType</span></span>|<span data-ttu-id="4f992-121">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung innerhalb einer Domäne mithilfe eines Proxys über HTTP verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4f992-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="4f992-122">Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet.</span><span class="sxs-lookup"><span data-stu-id="4f992-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="4f992-123">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="4f992-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="4f992-124">realm</span><span class="sxs-lookup"><span data-stu-id="4f992-124">realm</span></span>|<span data-ttu-id="4f992-125">Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="4f992-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="4f992-126">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4f992-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="4f992-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="4f992-127">policyEnforcement</span></span>|<span data-ttu-id="4f992-128">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4f992-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="4f992-129">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="4f992-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="4f992-130">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4f992-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="4f992-131">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4f992-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="4f992-132">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="4f992-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="4f992-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="4f992-133">protectionScenario</span></span>|<span data-ttu-id="4f992-134">Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.</span><span class="sxs-lookup"><span data-stu-id="4f992-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="4f992-135">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="4f992-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4f992-136">Wert</span><span class="sxs-lookup"><span data-stu-id="4f992-136">Value</span></span>|<span data-ttu-id="4f992-137">Description</span><span class="sxs-lookup"><span data-stu-id="4f992-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f992-138">None</span><span class="sxs-lookup"><span data-stu-id="4f992-138">None</span></span>|<span data-ttu-id="4f992-139">Nachrichten werden nicht während der Übertragung gesichert.</span><span class="sxs-lookup"><span data-stu-id="4f992-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="4f992-140">Einfach</span><span class="sxs-lookup"><span data-stu-id="4f992-140">Basic</span></span>|<span data-ttu-id="4f992-141">Gibt die Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="4f992-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="4f992-142">Digest</span><span class="sxs-lookup"><span data-stu-id="4f992-142">Digest</span></span>|<span data-ttu-id="4f992-143">Gibt die Digestauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="4f992-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="4f992-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="4f992-144">Ntlm</span></span>|<span data-ttu-id="4f992-145">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4f992-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="4f992-146">Windows</span><span class="sxs-lookup"><span data-stu-id="4f992-146">Windows</span></span>|<span data-ttu-id="4f992-147">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="4f992-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="4f992-148">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="4f992-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4f992-149">Wert</span><span class="sxs-lookup"><span data-stu-id="4f992-149">Value</span></span>|<span data-ttu-id="4f992-150">Description</span><span class="sxs-lookup"><span data-stu-id="4f992-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f992-151">None</span><span class="sxs-lookup"><span data-stu-id="4f992-151">None</span></span>|<span data-ttu-id="4f992-152">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="4f992-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="4f992-153">Einfach</span><span class="sxs-lookup"><span data-stu-id="4f992-153">Basic</span></span>|<span data-ttu-id="4f992-154">Gibt die Standard Authentifizierung gemäß RFC 2617 – http-Authentifizierung an: Standard-und Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f992-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="4f992-155">Digest</span><span class="sxs-lookup"><span data-stu-id="4f992-155">Digest</span></span>|<span data-ttu-id="4f992-156">Gibt die Digest-Authentifizierung gemäß RFC 2617 – http-Authentifizierung an: Standard-und Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f992-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="4f992-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="4f992-157">Ntlm</span></span>|<span data-ttu-id="4f992-158">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4f992-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="4f992-159">Windows</span><span class="sxs-lookup"><span data-stu-id="4f992-159">Windows</span></span>|<span data-ttu-id="4f992-160">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="4f992-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="4f992-161">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4f992-161">Certificate</span></span>|<span data-ttu-id="4f992-162">Führt die Clientauthentifizierung mit einem Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="4f992-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="4f992-163">Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="4f992-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f992-164">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f992-164">Child Elements</span></span>  
 <span data-ttu-id="4f992-165">None</span><span class="sxs-lookup"><span data-stu-id="4f992-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f992-166">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f992-166">Parent Elements</span></span>  
  
|<span data-ttu-id="4f992-167">Element</span><span class="sxs-lookup"><span data-stu-id="4f992-167">Element</span></span>|<span data-ttu-id="4f992-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f992-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f992-169">\<security></span><span class="sxs-lookup"><span data-stu-id="4f992-169">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="4f992-170">Definiert die Sicherheitsfunktionen für die [ \<> "netthttpbinding](nethttpbinding.md)".</span><span class="sxs-lookup"><span data-stu-id="4f992-170">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4f992-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f992-171">Example</span></span>  
 <span data-ttu-id="4f992-172">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4f992-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="4f992-173">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="4f992-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f992-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f992-174">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="4f992-175">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="4f992-175">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4f992-176">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f992-176">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4f992-177">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f992-177">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4f992-178">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4f992-178">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4f992-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f992-179">\<binding></span></span>](../../../misc/binding.md)
