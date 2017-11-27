---
title: '&lt;transport&gt; von &lt;basicHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a69be01146e71e71ba7e901de288d84c533b1e1c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltbasichttpbindinggt"></a><span data-ttu-id="2fae4-102">&lt;transport&gt; von &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="2fae4-102">&lt;transport&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="2fae4-103">Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.</span><span class="sxs-lookup"><span data-stu-id="2fae4-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
 <span data-ttu-id="2fae4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2fae4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2fae4-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="2fae4-105">\<bindings></span></span>  
<span data-ttu-id="2fae4-106">\<BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2fae4-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="2fae4-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="2fae4-107">\<binding></span></span>  
<span data-ttu-id="2fae4-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="2fae4-108">\<security></span></span>  
<span data-ttu-id="2fae4-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="2fae4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fae4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fae4-110">Syntax</span></span>  
  
```xml  
<basicHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fae4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2fae4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2fae4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fae4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fae4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2fae4-113">Attributes</span></span>  
  
|<span data-ttu-id="2fae4-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="2fae4-114">Attribute</span></span>|<span data-ttu-id="2fae4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fae4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2fae4-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2fae4-116">clientCredentialType</span></span>|<span data-ttu-id="2fae4-117">-Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit HTTP-Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fae4-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="2fae4-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="2fae4-118">The default is `None`.</span></span> <span data-ttu-id="2fae4-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2fae4-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="2fae4-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="2fae4-120">proxyCredentialType</span></span>|<span data-ttu-id="2fae4-121">-Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung innerhalb einer Domäne mit einem Proxy über HTTP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fae4-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="2fae4-122">Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet.</span><span class="sxs-lookup"><span data-stu-id="2fae4-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="2fae4-123">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2fae4-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="2fae4-124">realm</span><span class="sxs-lookup"><span data-stu-id="2fae4-124">realm</span></span>|<span data-ttu-id="2fae4-125">Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Digest- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="2fae4-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="2fae4-126">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2fae4-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="2fae4-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="2fae4-127">policyEnforcement</span></span>|<span data-ttu-id="2fae4-128">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2fae4-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="2fae4-129">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="2fae4-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="2fae4-130">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fae4-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="2fae4-131">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="2fae4-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="2fae4-132">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="2fae4-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="2fae4-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="2fae4-133">protectionScenario</span></span>|<span data-ttu-id="2fae4-134">Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.</span><span class="sxs-lookup"><span data-stu-id="2fae4-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="2fae4-135">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="2fae4-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2fae4-136">Wert</span><span class="sxs-lookup"><span data-stu-id="2fae4-136">Value</span></span>|<span data-ttu-id="2fae4-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fae4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2fae4-138">Keine</span><span class="sxs-lookup"><span data-stu-id="2fae4-138">None</span></span>|<span data-ttu-id="2fae4-139">Nachrichten werden nicht während der Übertragung gesichert.</span><span class="sxs-lookup"><span data-stu-id="2fae4-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2fae4-140">Standard</span><span class="sxs-lookup"><span data-stu-id="2fae4-140">Basic</span></span>|<span data-ttu-id="2fae4-141">Gibt die Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="2fae4-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="2fae4-142">Digest</span><span class="sxs-lookup"><span data-stu-id="2fae4-142">Digest</span></span>|<span data-ttu-id="2fae4-143">Gibt die Digestauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="2fae4-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="2fae4-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2fae4-144">Ntlm</span></span>|<span data-ttu-id="2fae4-145">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="2fae4-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="2fae4-146">Windows</span><span class="sxs-lookup"><span data-stu-id="2fae4-146">Windows</span></span>|<span data-ttu-id="2fae4-147">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="2fae4-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="2fae4-148">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="2fae4-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2fae4-149">Wert</span><span class="sxs-lookup"><span data-stu-id="2fae4-149">Value</span></span>|<span data-ttu-id="2fae4-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fae4-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2fae4-151">Keine</span><span class="sxs-lookup"><span data-stu-id="2fae4-151">None</span></span>|<span data-ttu-id="2fae4-152">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="2fae4-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2fae4-153">Standard</span><span class="sxs-lookup"><span data-stu-id="2fae4-153">Basic</span></span>|<span data-ttu-id="2fae4-154">Gibt die Standardauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="2fae4-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="2fae4-155">Digest</span><span class="sxs-lookup"><span data-stu-id="2fae4-155">Digest</span></span>|<span data-ttu-id="2fae4-156">Gibt die Digestauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="2fae4-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="2fae4-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2fae4-157">Ntlm</span></span>|<span data-ttu-id="2fae4-158">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="2fae4-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="2fae4-159">Windows</span><span class="sxs-lookup"><span data-stu-id="2fae4-159">Windows</span></span>|<span data-ttu-id="2fae4-160">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="2fae4-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="2fae4-161">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="2fae4-161">Certificate</span></span>|<span data-ttu-id="2fae4-162">Führt die Clientauthentifizierung mit einem Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="2fae4-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="2fae4-163">Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="2fae4-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2fae4-164">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fae4-164">Child Elements</span></span>  
 <span data-ttu-id="2fae4-165">Keine</span><span class="sxs-lookup"><span data-stu-id="2fae4-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2fae4-166">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fae4-166">Parent Elements</span></span>  
  
|<span data-ttu-id="2fae4-167">Element</span><span class="sxs-lookup"><span data-stu-id="2fae4-167">Element</span></span>|<span data-ttu-id="2fae4-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fae4-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fae4-169">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="2fae4-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="2fae4-170">Definiert die Sicherheitsfunktionen für die [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2fae4-170">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2fae4-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fae4-171">Example</span></span>  
 <span data-ttu-id="2fae4-172">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2fae4-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="2fae4-173">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="2fae4-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fae4-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fae4-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="2fae4-175">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2fae4-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="2fae4-176">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2fae4-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2fae4-177">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2fae4-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="2fae4-178">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2fae4-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="2fae4-179">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="2fae4-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
