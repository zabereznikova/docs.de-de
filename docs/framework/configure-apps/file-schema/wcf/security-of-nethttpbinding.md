---
title: '&lt;security&gt; von &lt;netHttpBinding'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbe36a801565af0d3664e5c827f8ce903be3b5c7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="48126-102">&lt;security&gt; von &lt;netHttpBinding</span><span class="sxs-lookup"><span data-stu-id="48126-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="48126-103">Definiert die Sicherheitsfunktionen des der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="48126-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="48126-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="48126-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="48126-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="48126-105">\<bindings></span></span>  
<span data-ttu-id="48126-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="48126-106">\<netHttpBinding></span></span>  
<span data-ttu-id="48126-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="48126-107">\<binding></span></span>  
<span data-ttu-id="48126-108">\<security></span><span class="sxs-lookup"><span data-stu-id="48126-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48126-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="48126-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48126-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="48126-110">Attributes and Elements</span></span>  
 <span data-ttu-id="48126-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48126-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48126-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="48126-112">Attributes</span></span>  
  
|<span data-ttu-id="48126-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="48126-113">Attribute</span></span>|<span data-ttu-id="48126-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48126-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48126-115">Modus</span><span class="sxs-lookup"><span data-stu-id="48126-115">mode</span></span>|<span data-ttu-id="48126-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="48126-116">Optional.</span></span> <span data-ttu-id="48126-117">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="48126-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="48126-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="48126-118">The default is `None`.</span></span> <span data-ttu-id="48126-119">Dieses Attribut ist vom Typ <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`.</span><span class="sxs-lookup"><span data-stu-id="48126-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="48126-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="48126-120">mode Attribute</span></span>  
  
|<span data-ttu-id="48126-121">Wert</span><span class="sxs-lookup"><span data-stu-id="48126-121">Value</span></span>|<span data-ttu-id="48126-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48126-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="48126-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="48126-123">None</span></span>|<span data-ttu-id="48126-124">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="48126-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="48126-125">Transport</span><span class="sxs-lookup"><span data-stu-id="48126-125">Transport</span></span>|<span data-ttu-id="48126-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="48126-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="48126-127">Die SOAP-Nachrichten werden über HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="48126-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="48126-128">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="48126-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="48126-129">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="48126-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="48126-130">Meldung</span><span class="sxs-lookup"><span data-stu-id="48126-130">Message</span></span>|<span data-ttu-id="48126-131">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="48126-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="48126-132">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="48126-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="48126-133">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="48126-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="48126-134">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="48126-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="48126-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="48126-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="48126-136">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="48126-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="48126-137">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="48126-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="48126-138">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="48126-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="48126-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="48126-139">TransportCredentialOnly</span></span>|<span data-ttu-id="48126-140">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="48126-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="48126-141">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="48126-141">It provides http-based client authentication.</span></span> <span data-ttu-id="48126-142">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="48126-142">This mode should be used with caution.</span></span> <span data-ttu-id="48126-143">Er ist nur für Umgebungen geeignet, in denen die Transportsicherheit mit anderen Mitteln sichergestellt wird (z.&#160;B. durch IPSec) und nur die Clientauthentifizierung über die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="48126-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48126-144">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48126-144">Child Elements</span></span>  
  
|<span data-ttu-id="48126-145">Element</span><span class="sxs-lookup"><span data-stu-id="48126-145">Element</span></span>|<span data-ttu-id="48126-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48126-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48126-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="48126-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="48126-148">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="48126-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="48126-149">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="48126-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="48126-150">\<message></span><span class="sxs-lookup"><span data-stu-id="48126-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="48126-151">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="48126-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="48126-152">Dieses Element entspricht <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="48126-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48126-153">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48126-153">Parent Elements</span></span>  
  
|<span data-ttu-id="48126-154">Element</span><span class="sxs-lookup"><span data-stu-id="48126-154">Element</span></span>|<span data-ttu-id="48126-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48126-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48126-156">Bindung</span><span class="sxs-lookup"><span data-stu-id="48126-156">binding</span></span>|<span data-ttu-id="48126-157">Das Bindungselement, das von der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="48126-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48126-158">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48126-158">Remarks</span></span>  
 <span data-ttu-id="48126-159">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="48126-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="48126-160">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `netHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="48126-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48126-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48126-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <span data-ttu-id="48126-162"><xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A></span><span class="sxs-lookup"><span data-stu-id="48126-162"><xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A></span></span>    
 [<span data-ttu-id="48126-163">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="48126-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="48126-164">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="48126-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="48126-165">Bindungen</span><span class="sxs-lookup"><span data-stu-id="48126-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="48126-166">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="48126-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="48126-167">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="48126-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="48126-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="48126-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
