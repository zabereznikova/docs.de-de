---
title: <transport> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735936"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="5a7e1-102">\<transport> von \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="5a7e1-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="5a7e1-103">Definiert den Typ der Sicherheitsanforderungen auf Nachrichten Ebene für einen Endpunkt, der mit dem [\<NetTcpBinding->](nettcpbinding.md)konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="5a7e1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5a7e1-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="5a7e1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5a7e1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5a7e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetTcpBinding**](nettcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="5a7e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="5a7e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="5a7e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5a7e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="5a7e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport >**</span><span class="sxs-lookup"><span data-stu-id="5a7e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7e1-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a7e1-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a7e1-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a7e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5a7e1-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a7e1-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a7e1-114">Attributes</span></span>  
  
|<span data-ttu-id="5a7e1-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="5a7e1-115">Attribute</span></span>|<span data-ttu-id="5a7e1-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a7e1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a7e1-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="5a7e1-117">clientCredentialType</span></span>|<span data-ttu-id="5a7e1-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-118">Optional.</span></span> <span data-ttu-id="5a7e1-119">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="5a7e1-120">-Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="5a7e1-121">: Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="5a7e1-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="5a7e1-122">protectionLevel</span></span>|<span data-ttu-id="5a7e1-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-123">Optional.</span></span> <span data-ttu-id="5a7e1-124">Definiert die Sicherheit auf der Ebene des TCP-Transports.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="5a7e1-125">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="5a7e1-126">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="5a7e1-127">Der Standardwert ist `EncryptAndSign`sein.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="5a7e1-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="5a7e1-128">sslProtocols</span></span>|<span data-ttu-id="5a7e1-129">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="5a7e1-130">Der Standardwert ist&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="5a7e1-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="5a7e1-131">policyEnforcement</span></span>|<span data-ttu-id="5a7e1-132">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="5a7e1-133">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="5a7e1-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="5a7e1-134">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="5a7e1-135">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="5a7e1-136">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="5a7e1-137">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="5a7e1-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5a7e1-138">Wert</span><span class="sxs-lookup"><span data-stu-id="5a7e1-138">Value</span></span>|<span data-ttu-id="5a7e1-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a7e1-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a7e1-140">Keiner</span><span class="sxs-lookup"><span data-stu-id="5a7e1-140">None</span></span>|<span data-ttu-id="5a7e1-141">Der Client ist anonym.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-141">The client is anonymous.</span></span> <span data-ttu-id="5a7e1-142">Dies erfordert ein Zertifikat für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="5a7e1-143">Windows</span><span class="sxs-lookup"><span data-stu-id="5a7e1-143">Windows</span></span>|<span data-ttu-id="5a7e1-144">Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="5a7e1-145">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="5a7e1-145">Certificate</span></span>|<span data-ttu-id="5a7e1-146">Der Client wird mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="5a7e1-147">Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="5a7e1-148">protectionLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="5a7e1-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="5a7e1-149">Wert</span><span class="sxs-lookup"><span data-stu-id="5a7e1-149">Value</span></span>|<span data-ttu-id="5a7e1-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a7e1-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a7e1-151">Keiner</span><span class="sxs-lookup"><span data-stu-id="5a7e1-151">None</span></span>|<span data-ttu-id="5a7e1-152">Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-152">No protection.</span></span>|  
|<span data-ttu-id="5a7e1-153">Sign</span><span class="sxs-lookup"><span data-stu-id="5a7e1-153">Sign</span></span>|<span data-ttu-id="5a7e1-154">Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-154">Messages are signed.</span></span>|  
|<span data-ttu-id="5a7e1-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="5a7e1-155">EncryptAndSign</span></span>|<span data-ttu-id="5a7e1-156">-Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a7e1-157">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a7e1-157">Child Elements</span></span>  
 <span data-ttu-id="5a7e1-158">Keiner</span><span class="sxs-lookup"><span data-stu-id="5a7e1-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a7e1-159">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a7e1-159">Parent Elements</span></span>  
  
|<span data-ttu-id="5a7e1-160">Element</span><span class="sxs-lookup"><span data-stu-id="5a7e1-160">Element</span></span>|<span data-ttu-id="5a7e1-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a7e1-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a7e1-162">\<Security ></span><span class="sxs-lookup"><span data-stu-id="5a7e1-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="5a7e1-163">Gibt die Sicherheitsfunktionen des [\<NetTcpBinding->](nettcpbinding.md)an.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a7e1-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a7e1-164">Remarks</span></span>  
 <span data-ttu-id="5a7e1-165">Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="5a7e1-166">Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.</span><span class="sxs-lookup"><span data-stu-id="5a7e1-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7e1-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a7e1-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="5a7e1-168">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5a7e1-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5a7e1-169">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5a7e1-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5a7e1-170">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5a7e1-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5a7e1-171">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5a7e1-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5a7e1-172">\<binding ></span><span class="sxs-lookup"><span data-stu-id="5a7e1-172">\<binding></span></span>](bindings.md)
