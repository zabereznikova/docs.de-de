---
title: '&lt;security&gt; von &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2adb5736cca59d42ab3c62d61513bbfd80a4be04
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138304"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="bf4c7-102">&lt;security&gt; von &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="bf4c7-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="bf4c7-103">Definiert die Sicherheitsfunktionen von der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bf4c7-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="bf4c7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bf4c7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bf4c7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bf4c7-105">\<bindings></span></span>  
<span data-ttu-id="bf4c7-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bf4c7-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="bf4c7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="bf4c7-107">\<binding></span></span>  
<span data-ttu-id="bf4c7-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="bf4c7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4c7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf4c7-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf4c7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf4c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bf4c7-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf4c7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf4c7-112">Attributes</span></span>  
  
|<span data-ttu-id="bf4c7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="bf4c7-113">Attribute</span></span>|<span data-ttu-id="bf4c7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf4c7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf4c7-115">Modus</span><span class="sxs-lookup"><span data-stu-id="bf4c7-115">mode</span></span>|<span data-ttu-id="bf4c7-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-116">Optional.</span></span> <span data-ttu-id="bf4c7-117">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="bf4c7-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-118">The default is `None`.</span></span> <span data-ttu-id="bf4c7-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="bf4c7-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="bf4c7-120">mode Attribute</span></span>  
  
|<span data-ttu-id="bf4c7-121">Wert</span><span class="sxs-lookup"><span data-stu-id="bf4c7-121">Value</span></span>|<span data-ttu-id="bf4c7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf4c7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bf4c7-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="bf4c7-123">None</span></span>|<span data-ttu-id="bf4c7-124">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="bf4c7-125">Transport</span><span class="sxs-lookup"><span data-stu-id="bf4c7-125">Transport</span></span>|<span data-ttu-id="bf4c7-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="bf4c7-127">Die SOAP-Nachrichten werden über HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="bf4c7-128">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="bf4c7-129">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="bf4c7-130">Finden Sie unter den [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bf4c7-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="bf4c7-131">Meldung</span><span class="sxs-lookup"><span data-stu-id="bf4c7-131">Message</span></span>|<span data-ttu-id="bf4c7-132">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="bf4c7-133">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="bf4c7-134">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="bf4c7-135">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="bf4c7-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="bf4c7-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="bf4c7-137">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="bf4c7-138">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="bf4c7-139">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="bf4c7-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="bf4c7-140">TransportCredentialOnly</span></span>|<span data-ttu-id="bf4c7-141">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="bf4c7-142">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-142">It provides http-based client authentication.</span></span> <span data-ttu-id="bf4c7-143">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-143">This mode should be used with caution.</span></span> <span data-ttu-id="bf4c7-144">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit durch andere Mittel (z. B. IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf4c7-145">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf4c7-145">Child Elements</span></span>  
  
|<span data-ttu-id="bf4c7-146">Element</span><span class="sxs-lookup"><span data-stu-id="bf4c7-146">Element</span></span>|<span data-ttu-id="bf4c7-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf4c7-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf4c7-148">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="bf4c7-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="bf4c7-149">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="bf4c7-150">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="bf4c7-151">\<message></span><span class="sxs-lookup"><span data-stu-id="bf4c7-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="bf4c7-152">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="bf4c7-153">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf4c7-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf4c7-154">Parent Elements</span></span>  
  
|<span data-ttu-id="bf4c7-155">Element</span><span class="sxs-lookup"><span data-stu-id="bf4c7-155">Element</span></span>|<span data-ttu-id="bf4c7-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf4c7-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bf4c7-157">Bindung</span><span class="sxs-lookup"><span data-stu-id="bf4c7-157">binding</span></span>|<span data-ttu-id="bf4c7-158">Das Bindungselement, das von der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bf4c7-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf4c7-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf4c7-159">Remarks</span></span>  
 <span data-ttu-id="bf4c7-160">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="bf4c7-161">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `basicHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf4c7-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4c7-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf4c7-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="bf4c7-163">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="bf4c7-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bf4c7-164">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="bf4c7-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="bf4c7-165">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bf4c7-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bf4c7-166">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bf4c7-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bf4c7-167">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bf4c7-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bf4c7-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="bf4c7-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
