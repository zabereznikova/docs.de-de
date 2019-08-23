---
title: <security> von <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: e627a63221d0013c89495d7ff81e02047a03df89
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936509"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="5e92b-102">\<Sicherheits > von \<WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="5e92b-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="5e92b-103">Stellt die Sicherheitsfunktionen des [ \<WSHttpBinding->](wshttpbinding.md)dar.</span><span class="sxs-lookup"><span data-stu-id="5e92b-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="5e92b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5e92b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e92b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5e92b-105">\<bindings></span></span>  
<span data-ttu-id="5e92b-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5e92b-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="5e92b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e92b-107">\<binding></span></span>  
<span data-ttu-id="5e92b-108">\<security></span><span class="sxs-lookup"><span data-stu-id="5e92b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e92b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e92b-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e92b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e92b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e92b-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e92b-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e92b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5e92b-112">Attributes</span></span>  
  
|<span data-ttu-id="5e92b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5e92b-113">Attribute</span></span>|<span data-ttu-id="5e92b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e92b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e92b-115">Modus</span><span class="sxs-lookup"><span data-stu-id="5e92b-115">mode</span></span>|<span data-ttu-id="5e92b-116">Optionale.</span><span class="sxs-lookup"><span data-stu-id="5e92b-116">-   Optional.</span></span> <span data-ttu-id="5e92b-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="5e92b-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5e92b-118">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="5e92b-118">The default is `Message`.</span></span><br /><span data-ttu-id="5e92b-119">: Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5e92b-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5e92b-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="5e92b-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="5e92b-121">Wert</span><span class="sxs-lookup"><span data-stu-id="5e92b-121">Value</span></span>|<span data-ttu-id="5e92b-122">Description</span><span class="sxs-lookup"><span data-stu-id="5e92b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e92b-123">None</span><span class="sxs-lookup"><span data-stu-id="5e92b-123">None</span></span>|<span data-ttu-id="5e92b-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5e92b-124">Security is disabled.</span></span>|  
|<span data-ttu-id="5e92b-125">Transport</span><span class="sxs-lookup"><span data-stu-id="5e92b-125">Transport</span></span>|<span data-ttu-id="5e92b-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5e92b-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="5e92b-127">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5e92b-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="5e92b-128">Die Nachricht wird vollständig über HTTPS gesichert und wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="5e92b-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="5e92b-129">Die Clientauthentifizierung wird durch das `ClientCredentials`-Attribut</span><span class="sxs-lookup"><span data-stu-id="5e92b-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="5e92b-130">des Transport [ >\<](transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5e92b-130">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="5e92b-131">Meldung</span><span class="sxs-lookup"><span data-stu-id="5e92b-131">Message</span></span>|<span data-ttu-id="5e92b-132">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5e92b-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="5e92b-133">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="5e92b-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="5e92b-134">Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmensammlung verwendet werden soll und welcher Schutzgrad über die Security.Message-Eigenschaft auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e92b-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="5e92b-135">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="5e92b-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="5e92b-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="5e92b-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="5e92b-137">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="5e92b-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="5e92b-138">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="5e92b-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e92b-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e92b-139">Child Elements</span></span>  
  
|<span data-ttu-id="5e92b-140">Element</span><span class="sxs-lookup"><span data-stu-id="5e92b-140">Element</span></span>|<span data-ttu-id="5e92b-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e92b-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e92b-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="5e92b-142">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="5e92b-143">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="5e92b-143">Defines the transport security settings.</span></span> <span data-ttu-id="5e92b-144">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="5e92b-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="5e92b-145">\<message></span><span class="sxs-lookup"><span data-stu-id="5e92b-145">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="5e92b-146">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5e92b-146">Defines the security settings for the message.</span></span> <span data-ttu-id="5e92b-147">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="5e92b-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e92b-148">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e92b-148">Parent Elements</span></span>  
  
|<span data-ttu-id="5e92b-149">Element</span><span class="sxs-lookup"><span data-stu-id="5e92b-149">Element</span></span>|<span data-ttu-id="5e92b-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e92b-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e92b-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5e92b-151">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="5e92b-152">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="5e92b-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e92b-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e92b-153">Remarks</span></span>  
 <span data-ttu-id="5e92b-154">Die WSHttpBinding-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="5e92b-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="5e92b-155">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e92b-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e92b-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e92b-156">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="5e92b-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5e92b-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5e92b-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5e92b-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5e92b-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5e92b-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5e92b-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5e92b-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5e92b-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e92b-161">\<binding></span></span>](../../../misc/binding.md)
