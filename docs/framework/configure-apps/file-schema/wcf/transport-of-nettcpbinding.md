---
title: <transport> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 8f752373c51992c51b747f5f4dc4a63910a387c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162191"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="7e22e-102">\<transport> von \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="7e22e-102">\<transport> of \<netTcpBinding></span></span>

<span data-ttu-id="7e22e-103">Definiert den Typ der Sicherheitsanforderungen auf Nachrichten Ebene für einen Endpunkt, der mit konfiguriert wurde [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7e22e-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="7e22e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e22e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e22e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7e22e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7e22e-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e22e-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e22e-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="7e22e-107">Attributes</span></span>  
  
|<span data-ttu-id="7e22e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7e22e-108">Attribute</span></span>|<span data-ttu-id="7e22e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e22e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e22e-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7e22e-110">clientCredentialType</span></span>|<span data-ttu-id="7e22e-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7e22e-111">Optional.</span></span> <span data-ttu-id="7e22e-112">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e22e-112">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="7e22e-113">-Der Standardwert ist `Windows` .</span><span class="sxs-lookup"><span data-stu-id="7e22e-113">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="7e22e-114">: Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="7e22e-114">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="7e22e-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7e22e-115">protectionLevel</span></span>|<span data-ttu-id="7e22e-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7e22e-116">Optional.</span></span> <span data-ttu-id="7e22e-117">Definiert die Sicherheit auf der Ebene des TCP-Transports.</span><span class="sxs-lookup"><span data-stu-id="7e22e-117">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="7e22e-118">Das Signieren von Nachrichten verringert das Risiko, dass Nachrichten während der Übertragung durch Dritte manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="7e22e-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="7e22e-119">Mit der Verschlüsselung können Daten während des Transports geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e22e-119">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="7e22e-120">Standardwert: `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="7e22e-120">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="7e22e-121">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="7e22e-121">sslProtocols</span></span>|<span data-ttu-id="7e22e-122">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e22e-122">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="7e22e-123">Der Standardwert ist TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="7e22e-123">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="7e22e-124">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="7e22e-124">policyEnforcement</span></span>|<span data-ttu-id="7e22e-125">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e22e-125">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="7e22e-126">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="7e22e-126">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="7e22e-127">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7e22e-127">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="7e22e-128">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="7e22e-128">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="7e22e-129">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="7e22e-129">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7e22e-130">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="7e22e-130">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7e22e-131">Wert</span><span class="sxs-lookup"><span data-stu-id="7e22e-131">Value</span></span>|<span data-ttu-id="7e22e-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e22e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e22e-133">Keine</span><span class="sxs-lookup"><span data-stu-id="7e22e-133">None</span></span>|<span data-ttu-id="7e22e-134">Der Client ist anonym.</span><span class="sxs-lookup"><span data-stu-id="7e22e-134">The client is anonymous.</span></span> <span data-ttu-id="7e22e-135">Dies erfordert ein Zertifikat für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="7e22e-135">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="7e22e-136">Windows</span><span class="sxs-lookup"><span data-stu-id="7e22e-136">Windows</span></span>|<span data-ttu-id="7e22e-137">Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.</span><span class="sxs-lookup"><span data-stu-id="7e22e-137">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="7e22e-138">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="7e22e-138">Certificate</span></span>|<span data-ttu-id="7e22e-139">Der Client wird mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="7e22e-139">The client is authenticated using a certificate.</span></span> <span data-ttu-id="7e22e-140">Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.</span><span class="sxs-lookup"><span data-stu-id="7e22e-140">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="7e22e-141">protectionLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="7e22e-141">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="7e22e-142">Wert</span><span class="sxs-lookup"><span data-stu-id="7e22e-142">Value</span></span>|<span data-ttu-id="7e22e-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e22e-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e22e-144">Keine</span><span class="sxs-lookup"><span data-stu-id="7e22e-144">None</span></span>|<span data-ttu-id="7e22e-145">Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="7e22e-145">No protection.</span></span>|  
|<span data-ttu-id="7e22e-146">Signieren</span><span class="sxs-lookup"><span data-stu-id="7e22e-146">Sign</span></span>|<span data-ttu-id="7e22e-147">Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="7e22e-147">Messages are signed.</span></span>|  
|<span data-ttu-id="7e22e-148">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="7e22e-148">EncryptAndSign</span></span>|<span data-ttu-id="7e22e-149">-Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="7e22e-149">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e22e-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e22e-150">Child Elements</span></span>  

 <span data-ttu-id="7e22e-151">Keine</span><span class="sxs-lookup"><span data-stu-id="7e22e-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e22e-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e22e-152">Parent Elements</span></span>  
  
|<span data-ttu-id="7e22e-153">Element</span><span class="sxs-lookup"><span data-stu-id="7e22e-153">Element</span></span>|<span data-ttu-id="7e22e-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e22e-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="7e22e-155">Gibt die Sicherheitsfunktionen des an [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7e22e-155">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e22e-156">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7e22e-156">Remarks</span></span>  

 <span data-ttu-id="7e22e-157">Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7e22e-157">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="7e22e-158">Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.</span><span class="sxs-lookup"><span data-stu-id="7e22e-158">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e22e-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e22e-159">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="7e22e-160">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7e22e-160">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7e22e-161">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7e22e-161">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7e22e-162">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7e22e-162">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7e22e-163">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7e22e-163">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
