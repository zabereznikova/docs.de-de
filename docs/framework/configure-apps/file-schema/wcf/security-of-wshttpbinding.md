---
title: '&lt;security&gt; von &lt;wsHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: de2fc0f562b079d5310ed2cd81211e14d4257515
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509695"
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="af4fa-102">&lt;security&gt; von &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="af4fa-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="af4fa-103">Gibt die Sicherheitsfunktionen von der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="af4fa-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="af4fa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="af4fa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="af4fa-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="af4fa-105">\<bindings></span></span>  
<span data-ttu-id="af4fa-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="af4fa-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="af4fa-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="af4fa-107">\<binding></span></span>  
<span data-ttu-id="af4fa-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="af4fa-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af4fa-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="af4fa-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af4fa-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af4fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af4fa-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af4fa-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af4fa-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="af4fa-112">Attributes</span></span>  
  
|<span data-ttu-id="af4fa-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="af4fa-113">Attribute</span></span>|<span data-ttu-id="af4fa-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af4fa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af4fa-115">mode</span><span class="sxs-lookup"><span data-stu-id="af4fa-115">mode</span></span>|<span data-ttu-id="af4fa-116">– Optional.</span><span class="sxs-lookup"><span data-stu-id="af4fa-116">-   Optional.</span></span> <span data-ttu-id="af4fa-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="af4fa-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="af4fa-118">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="af4fa-118">The default is `Message`.</span></span><br /><span data-ttu-id="af4fa-119">– Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="af4fa-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="af4fa-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="af4fa-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="af4fa-121">Wert</span><span class="sxs-lookup"><span data-stu-id="af4fa-121">Value</span></span>|<span data-ttu-id="af4fa-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af4fa-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af4fa-123">Keine</span><span class="sxs-lookup"><span data-stu-id="af4fa-123">None</span></span>|<span data-ttu-id="af4fa-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="af4fa-124">Security is disabled.</span></span>|  
|<span data-ttu-id="af4fa-125">Transport</span><span class="sxs-lookup"><span data-stu-id="af4fa-125">Transport</span></span>|<span data-ttu-id="af4fa-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="af4fa-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="af4fa-127">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="af4fa-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="af4fa-128">Die Nachricht wird vollständig über HTTPS gesichert und wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="af4fa-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="af4fa-129">Die Clientauthentifizierung wird durch das `ClientCredentials`-Attribut</span><span class="sxs-lookup"><span data-stu-id="af4fa-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="af4fa-130">von der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="af4fa-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="af4fa-131">Meldung</span><span class="sxs-lookup"><span data-stu-id="af4fa-131">Message</span></span>|<span data-ttu-id="af4fa-132">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="af4fa-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="af4fa-133">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="af4fa-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="af4fa-134">Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad über die Security.Message-Eigenschaft auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="af4fa-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="af4fa-135">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="af4fa-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="af4fa-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="af4fa-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="af4fa-137">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="af4fa-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="af4fa-138">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="af4fa-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af4fa-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af4fa-139">Child Elements</span></span>  
  
|<span data-ttu-id="af4fa-140">Element</span><span class="sxs-lookup"><span data-stu-id="af4fa-140">Element</span></span>|<span data-ttu-id="af4fa-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af4fa-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af4fa-142">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="af4fa-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="af4fa-143">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="af4fa-143">Defines the transport security settings.</span></span> <span data-ttu-id="af4fa-144">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="af4fa-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="af4fa-145">\<message></span><span class="sxs-lookup"><span data-stu-id="af4fa-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="af4fa-146">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="af4fa-146">Defines the security settings for the message.</span></span> <span data-ttu-id="af4fa-147">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="af4fa-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af4fa-148">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af4fa-148">Parent Elements</span></span>  
  
|<span data-ttu-id="af4fa-149">Element</span><span class="sxs-lookup"><span data-stu-id="af4fa-149">Element</span></span>|<span data-ttu-id="af4fa-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af4fa-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af4fa-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="af4fa-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="af4fa-152">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="af4fa-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af4fa-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af4fa-153">Remarks</span></span>  
 <span data-ttu-id="af4fa-154">Die WSHttpBinding-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="af4fa-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="af4fa-155">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="af4fa-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4fa-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af4fa-156">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [<span data-ttu-id="af4fa-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="af4fa-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="af4fa-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="af4fa-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="af4fa-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="af4fa-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="af4fa-160">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="af4fa-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="af4fa-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="af4fa-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
