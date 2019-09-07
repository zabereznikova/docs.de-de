---
title: <transport> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 41f11be9b4ae8f7a7535c9766965de8575cff784
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399323"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="2f534-102">\<transport> von \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="2f534-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="2f534-103">Definiert den Typ der Sicherheitsanforderungen auf Nachrichten Ebene für einen Endpunkt, der mit dem [ \<NetTcpBinding->](nettcpbinding.md)konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="2f534-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="2f534-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f534-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f534-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f534-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f534-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2f534-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2f534-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetTcpBinding->** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f534-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="2f534-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="2f534-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2f534-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f534-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="2f534-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Transport >**</span><span class="sxs-lookup"><span data-stu-id="2f534-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f534-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f534-111">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f534-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f534-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2f534-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f534-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f534-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f534-114">Attributes</span></span>  
  
|<span data-ttu-id="2f534-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="2f534-115">Attribute</span></span>|<span data-ttu-id="2f534-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f534-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f534-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2f534-117">clientCredentialType</span></span>|<span data-ttu-id="2f534-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="2f534-118">Optional.</span></span> <span data-ttu-id="2f534-119">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f534-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="2f534-120">-Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="2f534-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="2f534-121">: Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2f534-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="2f534-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="2f534-122">protectionLevel</span></span>|<span data-ttu-id="2f534-123">Optional.</span><span class="sxs-lookup"><span data-stu-id="2f534-123">Optional.</span></span> <span data-ttu-id="2f534-124">Definiert die Sicherheit auf der Ebene des TCP-Transports.</span><span class="sxs-lookup"><span data-stu-id="2f534-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="2f534-125">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="2f534-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="2f534-126">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="2f534-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="2f534-127">Der Standardwert ist `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="2f534-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="2f534-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="2f534-128">sslProtocols</span></span>|<span data-ttu-id="2f534-129">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2f534-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="2f534-130">Der Standardwert ist&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="2f534-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="2f534-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="2f534-131">policyEnforcement</span></span>|<span data-ttu-id="2f534-132">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f534-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="2f534-133">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="2f534-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="2f534-134">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2f534-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="2f534-135">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="2f534-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="2f534-136">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="2f534-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="2f534-137">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="2f534-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2f534-138">Wert</span><span class="sxs-lookup"><span data-stu-id="2f534-138">Value</span></span>|<span data-ttu-id="2f534-139">Description</span><span class="sxs-lookup"><span data-stu-id="2f534-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f534-140">None</span><span class="sxs-lookup"><span data-stu-id="2f534-140">None</span></span>|<span data-ttu-id="2f534-141">Der Client ist anonym.</span><span class="sxs-lookup"><span data-stu-id="2f534-141">The client is anonymous.</span></span> <span data-ttu-id="2f534-142">Dies erfordert ein Zertifikat für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="2f534-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="2f534-143">Windows</span><span class="sxs-lookup"><span data-stu-id="2f534-143">Windows</span></span>|<span data-ttu-id="2f534-144">Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.</span><span class="sxs-lookup"><span data-stu-id="2f534-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="2f534-145">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="2f534-145">Certificate</span></span>|<span data-ttu-id="2f534-146">Der Client wird mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="2f534-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="2f534-147">Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.</span><span class="sxs-lookup"><span data-stu-id="2f534-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="2f534-148">protectionLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="2f534-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="2f534-149">Wert</span><span class="sxs-lookup"><span data-stu-id="2f534-149">Value</span></span>|<span data-ttu-id="2f534-150">Description</span><span class="sxs-lookup"><span data-stu-id="2f534-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f534-151">None</span><span class="sxs-lookup"><span data-stu-id="2f534-151">None</span></span>|<span data-ttu-id="2f534-152">Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="2f534-152">No protection.</span></span>|  
|<span data-ttu-id="2f534-153">Sign</span><span class="sxs-lookup"><span data-stu-id="2f534-153">Sign</span></span>|<span data-ttu-id="2f534-154">Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="2f534-154">Messages are signed.</span></span>|  
|<span data-ttu-id="2f534-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="2f534-155">EncryptAndSign</span></span>|<span data-ttu-id="2f534-156">-Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="2f534-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f534-157">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f534-157">Child Elements</span></span>  
 <span data-ttu-id="2f534-158">None</span><span class="sxs-lookup"><span data-stu-id="2f534-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f534-159">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f534-159">Parent Elements</span></span>  
  
|<span data-ttu-id="2f534-160">Element</span><span class="sxs-lookup"><span data-stu-id="2f534-160">Element</span></span>|<span data-ttu-id="2f534-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f534-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f534-162">\<security></span><span class="sxs-lookup"><span data-stu-id="2f534-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="2f534-163">Gibt die Sicherheitsfunktionen der [ \<NetTcpBinding->](nettcpbinding.md)an.</span><span class="sxs-lookup"><span data-stu-id="2f534-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f534-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f534-164">Remarks</span></span>  
 <span data-ttu-id="2f534-165">Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2f534-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="2f534-166">Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.</span><span class="sxs-lookup"><span data-stu-id="2f534-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f534-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f534-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="2f534-168">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2f534-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2f534-169">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2f534-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2f534-170">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2f534-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2f534-171">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2f534-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2f534-172">\<binding></span><span class="sxs-lookup"><span data-stu-id="2f534-172">\<binding></span></span>](../../../misc/binding.md)
