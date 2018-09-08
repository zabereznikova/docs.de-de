---
title: '&lt;security&gt; von &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2adb5736cca59d42ab3c62d61513bbfd80a4be04
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189909"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="7234b-102">&lt;security&gt; von &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7234b-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="7234b-103">Definiert die Sicherheitsfunktionen von der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7234b-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="7234b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7234b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7234b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7234b-105">\<bindings></span></span>  
<span data-ttu-id="7234b-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7234b-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="7234b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7234b-107">\<binding></span></span>  
<span data-ttu-id="7234b-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="7234b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7234b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7234b-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7234b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7234b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7234b-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7234b-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7234b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7234b-112">Attributes</span></span>  
  
|<span data-ttu-id="7234b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7234b-113">Attribute</span></span>|<span data-ttu-id="7234b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7234b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7234b-115">Modus</span><span class="sxs-lookup"><span data-stu-id="7234b-115">mode</span></span>|<span data-ttu-id="7234b-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7234b-116">Optional.</span></span> <span data-ttu-id="7234b-117">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="7234b-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="7234b-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="7234b-118">The default is `None`.</span></span> <span data-ttu-id="7234b-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7234b-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7234b-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="7234b-120">mode Attribute</span></span>  
  
|<span data-ttu-id="7234b-121">Wert</span><span class="sxs-lookup"><span data-stu-id="7234b-121">Value</span></span>|<span data-ttu-id="7234b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7234b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7234b-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="7234b-123">None</span></span>|<span data-ttu-id="7234b-124">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="7234b-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="7234b-125">Transport</span><span class="sxs-lookup"><span data-stu-id="7234b-125">Transport</span></span>|<span data-ttu-id="7234b-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7234b-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="7234b-127">Die SOAP-Nachrichten werden über HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="7234b-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="7234b-128">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="7234b-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="7234b-129">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="7234b-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="7234b-130">Finden Sie unter den [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7234b-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="7234b-131">Meldung</span><span class="sxs-lookup"><span data-stu-id="7234b-131">Message</span></span>|<span data-ttu-id="7234b-132">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7234b-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="7234b-133">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="7234b-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="7234b-134">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7234b-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="7234b-135">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="7234b-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="7234b-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7234b-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="7234b-137">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7234b-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="7234b-138">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7234b-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="7234b-139">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7234b-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="7234b-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="7234b-140">TransportCredentialOnly</span></span>|<span data-ttu-id="7234b-141">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="7234b-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="7234b-142">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7234b-142">It provides http-based client authentication.</span></span> <span data-ttu-id="7234b-143">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7234b-143">This mode should be used with caution.</span></span> <span data-ttu-id="7234b-144">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit durch andere Mittel (z. B. IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7234b-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7234b-145">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7234b-145">Child Elements</span></span>  
  
|<span data-ttu-id="7234b-146">Element</span><span class="sxs-lookup"><span data-stu-id="7234b-146">Element</span></span>|<span data-ttu-id="7234b-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7234b-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7234b-148">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="7234b-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="7234b-149">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="7234b-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="7234b-150">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="7234b-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="7234b-151">\<message></span><span class="sxs-lookup"><span data-stu-id="7234b-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="7234b-152">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="7234b-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="7234b-153">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="7234b-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7234b-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7234b-154">Parent Elements</span></span>  
  
|<span data-ttu-id="7234b-155">Element</span><span class="sxs-lookup"><span data-stu-id="7234b-155">Element</span></span>|<span data-ttu-id="7234b-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7234b-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7234b-157">Bindung</span><span class="sxs-lookup"><span data-stu-id="7234b-157">binding</span></span>|<span data-ttu-id="7234b-158">Das Bindungselement, das von der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7234b-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7234b-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7234b-159">Remarks</span></span>  
 <span data-ttu-id="7234b-160">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="7234b-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="7234b-161">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `basicHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7234b-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7234b-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7234b-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="7234b-163">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7234b-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="7234b-164">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="7234b-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="7234b-165">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7234b-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7234b-166">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7234b-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="7234b-167">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7234b-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="7234b-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="7234b-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
