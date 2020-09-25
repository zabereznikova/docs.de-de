---
title: <security> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: d39e3e5e655817aa91c5301274a860a00a6ab7ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169985"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="a4bc0-102">\<security> von \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="a4bc0-102">\<security> of \<netTcpBinding></span></span>

<span data-ttu-id="a4bc0-103">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="a4bc0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4bc0-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4bc0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a4bc0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a4bc0-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4bc0-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="a4bc0-107">Attributes</span></span>  
  
|<span data-ttu-id="a4bc0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a4bc0-108">Attribute</span></span>|<span data-ttu-id="a4bc0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4bc0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4bc0-110">Modus</span><span class="sxs-lookup"><span data-stu-id="a4bc0-110">mode</span></span>|<span data-ttu-id="a4bc0-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-111">Optional.</span></span> <span data-ttu-id="a4bc0-112">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a4bc0-113">Gültige Werte werden unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-113">Valid values are shown below.</span></span> <span data-ttu-id="a4bc0-114">Standardwert: `Transport`.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="a4bc0-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a4bc0-116">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="a4bc0-116">mode Attribute</span></span>  
  
|<span data-ttu-id="a4bc0-117">Wert</span><span class="sxs-lookup"><span data-stu-id="a4bc0-117">Value</span></span>|<span data-ttu-id="a4bc0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4bc0-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4bc0-119">Keine</span><span class="sxs-lookup"><span data-stu-id="a4bc0-119">None</span></span>|<span data-ttu-id="a4bc0-120">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-120">Security is disabled.</span></span>|  
|<span data-ttu-id="a4bc0-121">Transport</span><span class="sxs-lookup"><span data-stu-id="a4bc0-121">Transport</span></span>|<span data-ttu-id="a4bc0-122">Die Transportsicherheit wird durch TLS über TCP oder SPNego gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="a4bc0-123">Der Dienst muss unter Umständen mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="a4bc0-124">In diesem Modus kann die Schutzstufe gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="a4bc0-125">`Message`</span><span class="sxs-lookup"><span data-stu-id="a4bc0-125">Message</span></span>|<span data-ttu-id="a4bc0-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a4bc0-127">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="a4bc0-128">Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmensammlung verwendet werden soll und welcher Schutzgrad auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="a4bc0-129">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="a4bc0-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a4bc0-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="a4bc0-131">Die Transportsicherheit wird mit der Nachrichtensicherheit gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="a4bc0-132">Die Transportsicherheit wird durch TLS über TCP oder SPNego bereitgestellt und stellt Integrität, Vertraulichkeit und Serverauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="a4bc0-133">Die Clientauthentifizierung wird durch die SOAP-Nachrichtensicherheit gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="a4bc0-134">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4bc0-135">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4bc0-135">Child Elements</span></span>  
  
|<span data-ttu-id="a4bc0-136">Element</span><span class="sxs-lookup"><span data-stu-id="a4bc0-136">Element</span></span>|<span data-ttu-id="a4bc0-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4bc0-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="a4bc0-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="a4bc0-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="a4bc0-140">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-140">Defines the security settings for the message.</span></span> <span data-ttu-id="a4bc0-141">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4bc0-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a4bc0-142">Parent Elements</span></span>  
  
|<span data-ttu-id="a4bc0-143">Element</span><span class="sxs-lookup"><span data-stu-id="a4bc0-143">Element</span></span>|<span data-ttu-id="a4bc0-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4bc0-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4bc0-145">binding</span><span class="sxs-lookup"><span data-stu-id="a4bc0-145">binding</span></span>|<span data-ttu-id="a4bc0-146">Das Bindungs Element von [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="a4bc0-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4bc0-147">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a4bc0-147">Remarks</span></span>  

 <span data-ttu-id="a4bc0-148">Alle Standardbindungen stellen Parameter zur Steuerung der Sicherheitsanforderungen für Übertragungen bereit.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="a4bc0-149">Diese Parameter beinhalten normalerweise den Sicherheitsmodus, mit dem angegeben wurde, ob Sicherheit auf Nachrichtenebene oder auf Übertragungsebene verwendet wird und welcher Clientanmeldeinformationstyp ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="a4bc0-150">Basierend auf der mit diesen Parametern bereitgestellten Optionsauswahl wird ein Kanalstapel mit der entsprechenden Sicherheit erstellt.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="a4bc0-151">Die von Windows Communication Foundation (WCF) gelieferten und vom System bereitgestellten Bindungen wurden für einige der gängigsten Szenarioanforderungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="a4bc0-152">Diese Bindungen ermöglichen alle die Angabe von Sicherheitsanforderungen für einige bestimmte Zielszenarien.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="a4bc0-153">Dieses Konfigurationselement stellt die Sicherheitsspezifikationen für `netTcpBinding` bereit.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="a4bc0-154">Daraus ergibt sich eine sichere, zuverlässige und optimierte Bindung, die computerübergreifende Kommunikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="a4bc0-155">Diese Bindung generiert standardmäßig einen Laufzeitkommunikationsstapel mit TCP für die Nachrichtenübertragung, Windows-Sicherheit für Nachrichtensicherheit und Authentifizierung, WS-Reliable-Messaging für Zuverlässigkeit sowie binäre Nachrichtencodierung.</span><span class="sxs-lookup"><span data-stu-id="a4bc0-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bc0-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4bc0-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="a4bc0-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a4bc0-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a4bc0-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a4bc0-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a4bc0-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a4bc0-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a4bc0-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a4bc0-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
