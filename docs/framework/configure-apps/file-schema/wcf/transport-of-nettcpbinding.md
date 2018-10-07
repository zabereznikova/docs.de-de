---
title: '&lt;transport&gt; von &lt;netTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 0405d3fa8e2155d21fd7bf5b20df39ff3db86b02
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48835793"
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a><span data-ttu-id="0ce94-102">&lt;transport&gt; von &lt;netTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="0ce94-102">&lt;transport&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="0ce94-103">Definiert den Typ der sicherheitsanforderungen auf Nachrichtenebene für einen Endpunkt konfiguriert, mit der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="0ce94-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="0ce94-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0ce94-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ce94-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0ce94-105">\<bindings></span></span>  
<span data-ttu-id="0ce94-106">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="0ce94-106">\<netTcpBinding></span></span>  
<span data-ttu-id="0ce94-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0ce94-107">\<binding></span></span>  
<span data-ttu-id="0ce94-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="0ce94-108">\<security></span></span>  
<span data-ttu-id="0ce94-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="0ce94-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce94-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ce94-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"             sslProtocols="Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ce94-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0ce94-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ce94-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ce94-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ce94-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ce94-113">Attributes</span></span>  
  
|<span data-ttu-id="0ce94-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="0ce94-114">Attribute</span></span>|<span data-ttu-id="0ce94-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ce94-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ce94-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0ce94-116">clientCredentialType</span></span>|<span data-ttu-id="0ce94-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0ce94-117">Optional.</span></span> <span data-ttu-id="0ce94-118">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ce94-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="0ce94-119">– Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="0ce94-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="0ce94-120">– Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0ce94-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="0ce94-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="0ce94-121">protectionLevel</span></span>|<span data-ttu-id="0ce94-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0ce94-122">Optional.</span></span> <span data-ttu-id="0ce94-123">Definiert die Sicherheit auf der Ebene des TCP-Transports.</span><span class="sxs-lookup"><span data-stu-id="0ce94-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="0ce94-124">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0ce94-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="0ce94-125">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="0ce94-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="0ce94-126">Der Standardwert ist `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="0ce94-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="0ce94-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="0ce94-127">sslProtocols</span></span>|<span data-ttu-id="0ce94-128">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0ce94-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="0ce94-129">Der Standardwert ist Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="0ce94-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="0ce94-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="0ce94-130">policyEnforcement</span></span>|<span data-ttu-id="0ce94-131">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ce94-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="0ce94-132">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="0ce94-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="0ce94-133">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0ce94-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="0ce94-134">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="0ce94-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="0ce94-135">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="0ce94-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="0ce94-136">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="0ce94-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0ce94-137">Wert</span><span class="sxs-lookup"><span data-stu-id="0ce94-137">Value</span></span>|<span data-ttu-id="0ce94-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ce94-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ce94-139">Keine</span><span class="sxs-lookup"><span data-stu-id="0ce94-139">None</span></span>|<span data-ttu-id="0ce94-140">Der Client ist anonym.</span><span class="sxs-lookup"><span data-stu-id="0ce94-140">The client is anonymous.</span></span> <span data-ttu-id="0ce94-141">Dies erfordert ein Zertifikat für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="0ce94-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="0ce94-142">Windows</span><span class="sxs-lookup"><span data-stu-id="0ce94-142">Windows</span></span>|<span data-ttu-id="0ce94-143">Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.</span><span class="sxs-lookup"><span data-stu-id="0ce94-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="0ce94-144">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="0ce94-144">Certificate</span></span>|<span data-ttu-id="0ce94-145">Der Client wird mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="0ce94-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="0ce94-146">Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.</span><span class="sxs-lookup"><span data-stu-id="0ce94-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="0ce94-147">protectionLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="0ce94-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="0ce94-148">Wert</span><span class="sxs-lookup"><span data-stu-id="0ce94-148">Value</span></span>|<span data-ttu-id="0ce94-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ce94-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ce94-150">Keine</span><span class="sxs-lookup"><span data-stu-id="0ce94-150">None</span></span>|<span data-ttu-id="0ce94-151">Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="0ce94-151">No protection.</span></span>|  
|<span data-ttu-id="0ce94-152">Sign</span><span class="sxs-lookup"><span data-stu-id="0ce94-152">Sign</span></span>|<span data-ttu-id="0ce94-153">Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="0ce94-153">Messages are signed.</span></span>|  
|<span data-ttu-id="0ce94-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="0ce94-154">EncryptAndSign</span></span>|<span data-ttu-id="0ce94-155">-Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="0ce94-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ce94-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ce94-156">Child Elements</span></span>  
 <span data-ttu-id="0ce94-157">Keiner</span><span class="sxs-lookup"><span data-stu-id="0ce94-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ce94-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ce94-158">Parent Elements</span></span>  
  
|<span data-ttu-id="0ce94-159">Element</span><span class="sxs-lookup"><span data-stu-id="0ce94-159">Element</span></span>|<span data-ttu-id="0ce94-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ce94-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ce94-161">\<security></span><span class="sxs-lookup"><span data-stu-id="0ce94-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="0ce94-162">Gibt an, die Sicherheitsfunktionen des der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="0ce94-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ce94-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ce94-163">Remarks</span></span>  
 <span data-ttu-id="0ce94-164">Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0ce94-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="0ce94-165">Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.</span><span class="sxs-lookup"><span data-stu-id="0ce94-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce94-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ce94-166">See Also</span></span>  
 <xref:System.ServiceModel.TcpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="0ce94-167">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="0ce94-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="0ce94-168">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0ce94-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0ce94-169">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0ce94-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="0ce94-170">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="0ce94-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="0ce94-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="0ce94-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
