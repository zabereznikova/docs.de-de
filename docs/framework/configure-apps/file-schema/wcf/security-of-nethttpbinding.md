---
title: <security> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736480"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="c827e-102">\<Sicherheits > der \<"netthttpbinding" ></span><span class="sxs-lookup"><span data-stu-id="c827e-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="c827e-103">Definiert die Sicherheitsfunktionen des [\<">](nethttpbinding.md)".</span><span class="sxs-lookup"><span data-stu-id="c827e-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="c827e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c827e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c827e-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="c827e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c827e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c827e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c827e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c827e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="c827e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="c827e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c827e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheit >**</span><span class="sxs-lookup"><span data-stu-id="c827e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c827e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c827e-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c827e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c827e-111">Attributes and elements</span></span>

<span data-ttu-id="c827e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c827e-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c827e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c827e-113">Attributes</span></span>

|<span data-ttu-id="c827e-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c827e-114">Attribute</span></span>|<span data-ttu-id="c827e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c827e-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="c827e-116">Modus</span><span class="sxs-lookup"><span data-stu-id="c827e-116">mode</span></span>|<span data-ttu-id="c827e-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c827e-117">Optional.</span></span> <span data-ttu-id="c827e-118">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="c827e-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="c827e-119">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="c827e-119">The default is `None`.</span></span> <span data-ttu-id="c827e-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c827e-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="c827e-121">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="c827e-121">mode attribute</span></span>

|<span data-ttu-id="c827e-122">Wert</span><span class="sxs-lookup"><span data-stu-id="c827e-122">Value</span></span>|<span data-ttu-id="c827e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c827e-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="c827e-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="c827e-124">None</span></span>|<span data-ttu-id="c827e-125">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="c827e-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="c827e-126">Transport</span><span class="sxs-lookup"><span data-stu-id="c827e-126">Transport</span></span>|<span data-ttu-id="c827e-127">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c827e-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="c827e-128">Die SOAP-Nachrichten werden über HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="c827e-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="c827e-129">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="c827e-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="c827e-130">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="c827e-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="c827e-131">Nachricht</span><span class="sxs-lookup"><span data-stu-id="c827e-131">Message</span></span>|<span data-ttu-id="c827e-132">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c827e-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="c827e-133">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="c827e-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="c827e-134">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c827e-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="c827e-135">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="c827e-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="c827e-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c827e-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="c827e-137">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c827e-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="c827e-138">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c827e-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="c827e-139">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c827e-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="c827e-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="c827e-140">TransportCredentialOnly</span></span>|<span data-ttu-id="c827e-141">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="c827e-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="c827e-142">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c827e-142">It provides http-based client authentication.</span></span> <span data-ttu-id="c827e-143">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c827e-143">This mode should be used with caution.</span></span> <span data-ttu-id="c827e-144">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c827e-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c827e-145">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c827e-145">Child elements</span></span>

|<span data-ttu-id="c827e-146">Element</span><span class="sxs-lookup"><span data-stu-id="c827e-146">Element</span></span>|<span data-ttu-id="c827e-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c827e-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c827e-148">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="c827e-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="c827e-149">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c827e-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="c827e-150">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="c827e-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="c827e-151">\<message ></span><span class="sxs-lookup"><span data-stu-id="c827e-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="c827e-152">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c827e-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="c827e-153">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="c827e-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c827e-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c827e-154">Parent elements</span></span>

|<span data-ttu-id="c827e-155">Element</span><span class="sxs-lookup"><span data-stu-id="c827e-155">Element</span></span>|<span data-ttu-id="c827e-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c827e-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="c827e-157">Bindung</span><span class="sxs-lookup"><span data-stu-id="c827e-157">binding</span></span>|<span data-ttu-id="c827e-158">Das Bindungs Element der [\<BasicHttpBinding->](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c827e-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="c827e-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c827e-159">Remarks</span></span>

 <span data-ttu-id="c827e-160">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="c827e-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="c827e-161">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `netHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c827e-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="c827e-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c827e-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="c827e-163">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c827e-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c827e-164">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="c827e-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="c827e-165">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c827e-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c827e-166">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c827e-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c827e-167">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c827e-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c827e-168">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c827e-168">\<binding></span></span>](bindings.md)
