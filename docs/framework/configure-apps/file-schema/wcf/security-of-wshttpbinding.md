---
title: '&lt;security&gt; von &lt;wsHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 7dfadcbb120f55232ea2375e880a5edb17caf045
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="cc918-102">&lt;security&gt; von &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="cc918-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="cc918-103">Stellt die Sicherheitsfunktionen des der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cc918-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="cc918-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cc918-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc918-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="cc918-105">\<bindings></span></span>  
<span data-ttu-id="cc918-106">\<WsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cc918-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="cc918-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="cc918-107">\<binding></span></span>  
<span data-ttu-id="cc918-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="cc918-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc918-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc918-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc918-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc918-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cc918-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc918-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc918-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc918-112">Attributes</span></span>  
  
|<span data-ttu-id="cc918-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="cc918-113">Attribute</span></span>|<span data-ttu-id="cc918-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc918-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc918-115">mode</span><span class="sxs-lookup"><span data-stu-id="cc918-115">mode</span></span>|<span data-ttu-id="cc918-116">-Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="cc918-116">-   Optional.</span></span> <span data-ttu-id="cc918-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="cc918-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="cc918-118">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="cc918-118">The default is `Message`.</span></span><br /><span data-ttu-id="cc918-119">– Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cc918-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="cc918-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="cc918-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="cc918-121">Wert</span><span class="sxs-lookup"><span data-stu-id="cc918-121">Value</span></span>|<span data-ttu-id="cc918-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc918-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cc918-123">Keine</span><span class="sxs-lookup"><span data-stu-id="cc918-123">None</span></span>|<span data-ttu-id="cc918-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cc918-124">Security is disabled.</span></span>|  
|<span data-ttu-id="cc918-125">Transport</span><span class="sxs-lookup"><span data-stu-id="cc918-125">Transport</span></span>|<span data-ttu-id="cc918-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cc918-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="cc918-127">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="cc918-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="cc918-128">Die Nachricht wird vollständig über HTTPS gesichert und wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="cc918-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="cc918-129">Die Clientauthentifizierung wird durch das `ClientCredentials`-Attribut</span><span class="sxs-lookup"><span data-stu-id="cc918-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="cc918-130">von der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cc918-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="cc918-131">Meldung</span><span class="sxs-lookup"><span data-stu-id="cc918-131">Message</span></span>|<span data-ttu-id="cc918-132">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cc918-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="cc918-133">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="cc918-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="cc918-134">Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad über die Security.Message-Eigenschaft auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc918-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="cc918-135">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="cc918-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="cc918-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="cc918-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="cc918-137">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="cc918-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="cc918-138">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="cc918-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc918-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc918-139">Child Elements</span></span>  
  
|<span data-ttu-id="cc918-140">Element</span><span class="sxs-lookup"><span data-stu-id="cc918-140">Element</span></span>|<span data-ttu-id="cc918-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc918-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc918-142">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="cc918-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="cc918-143">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="cc918-143">Defines the transport security settings.</span></span> <span data-ttu-id="cc918-144">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="cc918-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="cc918-145">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="cc918-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="cc918-146">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cc918-146">Defines the security settings for the message.</span></span> <span data-ttu-id="cc918-147">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="cc918-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc918-148">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc918-148">Parent Elements</span></span>  
  
|<span data-ttu-id="cc918-149">Element</span><span class="sxs-lookup"><span data-stu-id="cc918-149">Element</span></span>|<span data-ttu-id="cc918-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc918-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc918-151">\<WsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cc918-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="cc918-152">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="cc918-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc918-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc918-153">Remarks</span></span>  
 <span data-ttu-id="cc918-154">Die WSHttpBinding-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="cc918-154">The WSHttpBinding class is designed for interoperation with services that implement WS-* specifications.</span></span> <span data-ttu-id="cc918-155">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cc918-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc918-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc918-156">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [<span data-ttu-id="cc918-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="cc918-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="cc918-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="cc918-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cc918-159">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="cc918-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="cc918-160">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="cc918-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="cc918-161">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="cc918-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
