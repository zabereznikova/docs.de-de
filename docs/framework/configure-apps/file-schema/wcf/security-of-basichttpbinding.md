---
title: <security> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 00a933892376c2dc9771752beaf76d4994554968
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399893"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="ebb64-102">\<Sicherheits > von \<BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ebb64-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="ebb64-103">Definiert die Sicherheitsfunktionen des [ \<BasicHttpBinding->](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ebb64-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="ebb64-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ebb64-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ebb64-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ebb64-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ebb64-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ebb64-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ebb64-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BasicHttpBinding->** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ebb64-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="ebb64-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="ebb64-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ebb64-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="ebb64-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb64-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebb64-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebb64-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebb64-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ebb64-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebb64-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebb64-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebb64-113">Attributes</span></span>  
  
|<span data-ttu-id="ebb64-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ebb64-114">Attribute</span></span>|<span data-ttu-id="ebb64-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebb64-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ebb64-116">Modus</span><span class="sxs-lookup"><span data-stu-id="ebb64-116">mode</span></span>|<span data-ttu-id="ebb64-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="ebb64-117">Optional.</span></span> <span data-ttu-id="ebb64-118">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="ebb64-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="ebb64-119">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="ebb64-119">The default is `None`.</span></span> <span data-ttu-id="ebb64-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ebb64-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ebb64-121">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="ebb64-121">mode Attribute</span></span>  
  
|<span data-ttu-id="ebb64-122">Wert</span><span class="sxs-lookup"><span data-stu-id="ebb64-122">Value</span></span>|<span data-ttu-id="ebb64-123">Description</span><span class="sxs-lookup"><span data-stu-id="ebb64-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ebb64-124">None</span><span class="sxs-lookup"><span data-stu-id="ebb64-124">None</span></span>|<span data-ttu-id="ebb64-125">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="ebb64-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="ebb64-126">Transport</span><span class="sxs-lookup"><span data-stu-id="ebb64-126">Transport</span></span>|<span data-ttu-id="ebb64-127">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebb64-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="ebb64-128">Die SOAP-Nachrichten werden über HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="ebb64-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="ebb64-129">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ebb64-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="ebb64-130">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ebb64-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="ebb64-131">Weitere Informationen finden Sie unter [ \<Transport >](transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ebb64-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="ebb64-132">Meldung</span><span class="sxs-lookup"><span data-stu-id="ebb64-132">Message</span></span>|<span data-ttu-id="ebb64-133">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebb64-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="ebb64-134">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="ebb64-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="ebb64-135">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ebb64-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="ebb64-136">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="ebb64-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="ebb64-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="ebb64-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="ebb64-138">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebb64-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="ebb64-139">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebb64-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="ebb64-140">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ebb64-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="ebb64-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="ebb64-141">TransportCredentialOnly</span></span>|<span data-ttu-id="ebb64-142">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="ebb64-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="ebb64-143">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ebb64-143">It provides http-based client authentication.</span></span> <span data-ttu-id="ebb64-144">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebb64-144">This mode should be used with caution.</span></span> <span data-ttu-id="ebb64-145">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ebb64-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebb64-146">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebb64-146">Child Elements</span></span>  
  
|<span data-ttu-id="ebb64-147">Element</span><span class="sxs-lookup"><span data-stu-id="ebb64-147">Element</span></span>|<span data-ttu-id="ebb64-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebb64-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebb64-149">\<transport></span><span class="sxs-lookup"><span data-stu-id="ebb64-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="ebb64-150">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="ebb64-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="ebb64-151">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="ebb64-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="ebb64-152">\<message></span><span class="sxs-lookup"><span data-stu-id="ebb64-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="ebb64-153">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="ebb64-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="ebb64-154">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="ebb64-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ebb64-155">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebb64-155">Parent Elements</span></span>  
  
|<span data-ttu-id="ebb64-156">Element</span><span class="sxs-lookup"><span data-stu-id="ebb64-156">Element</span></span>|<span data-ttu-id="ebb64-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebb64-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebb64-158">Bindung</span><span class="sxs-lookup"><span data-stu-id="ebb64-158">binding</span></span>|<span data-ttu-id="ebb64-159">Das Bindungs Element des [ \<BasicHttpBinding->](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ebb64-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebb64-160">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebb64-160">Remarks</span></span>  
 <span data-ttu-id="ebb64-161">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ebb64-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="ebb64-162">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `basicHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ebb64-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb64-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebb64-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="ebb64-164">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ebb64-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ebb64-165">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="ebb64-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="ebb64-166">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ebb64-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ebb64-167">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ebb64-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ebb64-168">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ebb64-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ebb64-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="ebb64-169">\<binding></span></span>](../../../misc/binding.md)
