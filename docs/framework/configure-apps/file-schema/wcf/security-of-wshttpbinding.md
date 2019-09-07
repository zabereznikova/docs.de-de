---
title: <security> von <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: f7a4ef98637a7c966665fdd02ad26929bd4ba6ac
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399718"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="50bd8-102">\<Sicherheits > von \<WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="50bd8-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="50bd8-103">Stellt die Sicherheitsfunktionen des [ \<WSHttpBinding->](wshttpbinding.md)dar.</span><span class="sxs-lookup"><span data-stu-id="50bd8-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="50bd8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="50bd8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="50bd8-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="50bd8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="50bd8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="50bd8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="50bd8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSHttpBinding->** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="50bd8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="50bd8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="50bd8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="50bd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="50bd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50bd8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="50bd8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50bd8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="50bd8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="50bd8-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50bd8-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50bd8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="50bd8-113">Attributes</span></span>  
  
|<span data-ttu-id="50bd8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="50bd8-114">Attribute</span></span>|<span data-ttu-id="50bd8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50bd8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50bd8-116">Modus</span><span class="sxs-lookup"><span data-stu-id="50bd8-116">mode</span></span>|<span data-ttu-id="50bd8-117">Optionale.</span><span class="sxs-lookup"><span data-stu-id="50bd8-117">-   Optional.</span></span> <span data-ttu-id="50bd8-118">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="50bd8-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="50bd8-119">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="50bd8-119">The default is `Message`.</span></span><br /><span data-ttu-id="50bd8-120">: Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="50bd8-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="50bd8-121">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="50bd8-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="50bd8-122">Wert</span><span class="sxs-lookup"><span data-stu-id="50bd8-122">Value</span></span>|<span data-ttu-id="50bd8-123">Description</span><span class="sxs-lookup"><span data-stu-id="50bd8-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="50bd8-124">None</span><span class="sxs-lookup"><span data-stu-id="50bd8-124">None</span></span>|<span data-ttu-id="50bd8-125">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="50bd8-125">Security is disabled.</span></span>|  
|<span data-ttu-id="50bd8-126">Transport</span><span class="sxs-lookup"><span data-stu-id="50bd8-126">Transport</span></span>|<span data-ttu-id="50bd8-127">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="50bd8-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="50bd8-128">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="50bd8-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="50bd8-129">Die Nachricht wird vollständig über HTTPS gesichert und wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="50bd8-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="50bd8-130">Die Clientauthentifizierung wird durch das `ClientCredentials`-Attribut</span><span class="sxs-lookup"><span data-stu-id="50bd8-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="50bd8-131">des Transport [ >\<](transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="50bd8-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="50bd8-132">Meldung</span><span class="sxs-lookup"><span data-stu-id="50bd8-132">Message</span></span>|<span data-ttu-id="50bd8-133">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="50bd8-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="50bd8-134">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="50bd8-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="50bd8-135">Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmensammlung verwendet werden soll und welcher Schutzgrad über die Security.Message-Eigenschaft auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50bd8-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="50bd8-136">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="50bd8-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="50bd8-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="50bd8-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="50bd8-138">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="50bd8-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="50bd8-139">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="50bd8-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50bd8-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50bd8-140">Child Elements</span></span>  
  
|<span data-ttu-id="50bd8-141">Element</span><span class="sxs-lookup"><span data-stu-id="50bd8-141">Element</span></span>|<span data-ttu-id="50bd8-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50bd8-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50bd8-143">\<transport></span><span class="sxs-lookup"><span data-stu-id="50bd8-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="50bd8-144">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="50bd8-144">Defines the transport security settings.</span></span> <span data-ttu-id="50bd8-145">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="50bd8-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="50bd8-146">\<message></span><span class="sxs-lookup"><span data-stu-id="50bd8-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="50bd8-147">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="50bd8-147">Defines the security settings for the message.</span></span> <span data-ttu-id="50bd8-148">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="50bd8-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50bd8-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50bd8-149">Parent Elements</span></span>  
  
|<span data-ttu-id="50bd8-150">Element</span><span class="sxs-lookup"><span data-stu-id="50bd8-150">Element</span></span>|<span data-ttu-id="50bd8-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50bd8-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50bd8-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="50bd8-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="50bd8-153">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="50bd8-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50bd8-154">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50bd8-154">Remarks</span></span>  
 <span data-ttu-id="50bd8-155">Die WSHttpBinding-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="50bd8-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="50bd8-156">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="50bd8-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bd8-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50bd8-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="50bd8-158">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="50bd8-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="50bd8-159">Bindungen</span><span class="sxs-lookup"><span data-stu-id="50bd8-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="50bd8-160">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="50bd8-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="50bd8-161">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="50bd8-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="50bd8-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="50bd8-162">\<binding></span></span>](../../../misc/binding.md)
