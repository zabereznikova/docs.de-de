---
title: <transport> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 521aaf3913a1d30d10a674b71d4d98affcabc296
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399338"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="45aa2-102">\<Transport > von \<"netthttpbinding" ></span><span class="sxs-lookup"><span data-stu-id="45aa2-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="45aa2-103">Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.</span><span class="sxs-lookup"><span data-stu-id="45aa2-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="45aa2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="45aa2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="45aa2-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="45aa2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="45aa2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="45aa2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="45aa2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> "netthttpbinding"** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="45aa2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="45aa2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="45aa2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="45aa2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="45aa2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="45aa2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Transport >**</span><span class="sxs-lookup"><span data-stu-id="45aa2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45aa2-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="45aa2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45aa2-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="45aa2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="45aa2-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="45aa2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45aa2-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="45aa2-114">Attributes</span></span>  
  
|<span data-ttu-id="45aa2-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="45aa2-115">Attribute</span></span>|<span data-ttu-id="45aa2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45aa2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45aa2-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="45aa2-117">clientCredentialType</span></span>|<span data-ttu-id="45aa2-118">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung mithilfe der HTTP-Authentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="45aa2-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="45aa2-119">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="45aa2-119">The default is `None`.</span></span> <span data-ttu-id="45aa2-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="45aa2-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="45aa2-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="45aa2-121">proxyCredentialType</span></span>|<span data-ttu-id="45aa2-122">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung innerhalb einer Domäne mithilfe eines Proxys über HTTP verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="45aa2-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="45aa2-123">Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet.</span><span class="sxs-lookup"><span data-stu-id="45aa2-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="45aa2-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="45aa2-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="45aa2-125">realm</span><span class="sxs-lookup"><span data-stu-id="45aa2-125">realm</span></span>|<span data-ttu-id="45aa2-126">Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="45aa2-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="45aa2-127">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="45aa2-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="45aa2-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="45aa2-128">policyEnforcement</span></span>|<span data-ttu-id="45aa2-129">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="45aa2-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="45aa2-130">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="45aa2-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="45aa2-131">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45aa2-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="45aa2-132">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="45aa2-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="45aa2-133">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="45aa2-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="45aa2-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="45aa2-134">protectionScenario</span></span>|<span data-ttu-id="45aa2-135">Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.</span><span class="sxs-lookup"><span data-stu-id="45aa2-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="45aa2-136">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="45aa2-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="45aa2-137">Wert</span><span class="sxs-lookup"><span data-stu-id="45aa2-137">Value</span></span>|<span data-ttu-id="45aa2-138">Description</span><span class="sxs-lookup"><span data-stu-id="45aa2-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45aa2-139">None</span><span class="sxs-lookup"><span data-stu-id="45aa2-139">None</span></span>|<span data-ttu-id="45aa2-140">Nachrichten werden nicht während der Übertragung gesichert.</span><span class="sxs-lookup"><span data-stu-id="45aa2-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="45aa2-141">Einfach</span><span class="sxs-lookup"><span data-stu-id="45aa2-141">Basic</span></span>|<span data-ttu-id="45aa2-142">Gibt die Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="45aa2-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="45aa2-143">Digest</span><span class="sxs-lookup"><span data-stu-id="45aa2-143">Digest</span></span>|<span data-ttu-id="45aa2-144">Gibt die Digestauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="45aa2-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="45aa2-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="45aa2-145">Ntlm</span></span>|<span data-ttu-id="45aa2-146">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="45aa2-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="45aa2-147">Windows</span><span class="sxs-lookup"><span data-stu-id="45aa2-147">Windows</span></span>|<span data-ttu-id="45aa2-148">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="45aa2-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="45aa2-149">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="45aa2-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="45aa2-150">Wert</span><span class="sxs-lookup"><span data-stu-id="45aa2-150">Value</span></span>|<span data-ttu-id="45aa2-151">Description</span><span class="sxs-lookup"><span data-stu-id="45aa2-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45aa2-152">None</span><span class="sxs-lookup"><span data-stu-id="45aa2-152">None</span></span>|<span data-ttu-id="45aa2-153">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="45aa2-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="45aa2-154">Einfach</span><span class="sxs-lookup"><span data-stu-id="45aa2-154">Basic</span></span>|<span data-ttu-id="45aa2-155">Gibt die Standard Authentifizierung gemäß RFC 2617 – http-Authentifizierung an: Standard-und Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="45aa2-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="45aa2-156">Digest</span><span class="sxs-lookup"><span data-stu-id="45aa2-156">Digest</span></span>|<span data-ttu-id="45aa2-157">Gibt die Digest-Authentifizierung gemäß RFC 2617 – http-Authentifizierung an: Standard-und Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="45aa2-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="45aa2-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="45aa2-158">Ntlm</span></span>|<span data-ttu-id="45aa2-159">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="45aa2-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="45aa2-160">Windows</span><span class="sxs-lookup"><span data-stu-id="45aa2-160">Windows</span></span>|<span data-ttu-id="45aa2-161">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="45aa2-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="45aa2-162">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="45aa2-162">Certificate</span></span>|<span data-ttu-id="45aa2-163">Führt die Clientauthentifizierung mit einem Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="45aa2-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="45aa2-164">Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="45aa2-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45aa2-165">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45aa2-165">Child Elements</span></span>  
 <span data-ttu-id="45aa2-166">None</span><span class="sxs-lookup"><span data-stu-id="45aa2-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45aa2-167">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="45aa2-167">Parent Elements</span></span>  
  
|<span data-ttu-id="45aa2-168">Element</span><span class="sxs-lookup"><span data-stu-id="45aa2-168">Element</span></span>|<span data-ttu-id="45aa2-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45aa2-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45aa2-170">\<security></span><span class="sxs-lookup"><span data-stu-id="45aa2-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="45aa2-171">Definiert die Sicherheitsfunktionen für die [ \<> "netthttpbinding](nethttpbinding.md)".</span><span class="sxs-lookup"><span data-stu-id="45aa2-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="45aa2-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45aa2-172">Example</span></span>  
 <span data-ttu-id="45aa2-173">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="45aa2-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="45aa2-174">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="45aa2-174">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="45aa2-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45aa2-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="45aa2-176">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="45aa2-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="45aa2-177">Bindungen</span><span class="sxs-lookup"><span data-stu-id="45aa2-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="45aa2-178">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="45aa2-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="45aa2-179">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="45aa2-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="45aa2-180">\<binding></span><span class="sxs-lookup"><span data-stu-id="45aa2-180">\<binding></span></span>](../../../misc/binding.md)
