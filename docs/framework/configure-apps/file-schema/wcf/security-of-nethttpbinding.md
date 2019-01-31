---
title: <security> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283964"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="9de51-102">\<security> of \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9de51-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="9de51-103">Definiert die Sicherheitsfunktionen von der [ \<BasicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9de51-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>

<span data-ttu-id="9de51-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="9de51-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="9de51-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="9de51-105">\<bindings>\\</span></span>
<span data-ttu-id="9de51-106">\<netHttpBinding>\\</span><span class="sxs-lookup"><span data-stu-id="9de51-106">\<netHttpBinding>\\</span></span>
<span data-ttu-id="9de51-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="9de51-107">\<binding>\\</span></span>
<span data-ttu-id="9de51-108">\<security></span><span class="sxs-lookup"><span data-stu-id="9de51-108">\<security></span></span>

## <a name="syntax"></a><span data-ttu-id="9de51-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9de51-109">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9de51-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9de51-110">Attributes and elements</span></span>

<span data-ttu-id="9de51-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9de51-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9de51-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9de51-112">Attributes</span></span>

|<span data-ttu-id="9de51-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9de51-113">Attribute</span></span>|<span data-ttu-id="9de51-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9de51-114">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="9de51-115">Modus</span><span class="sxs-lookup"><span data-stu-id="9de51-115">mode</span></span>|<span data-ttu-id="9de51-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9de51-116">Optional.</span></span> <span data-ttu-id="9de51-117">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="9de51-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="9de51-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="9de51-118">The default is `None`.</span></span> <span data-ttu-id="9de51-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9de51-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="9de51-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="9de51-120">mode attribute</span></span>

|<span data-ttu-id="9de51-121">Wert</span><span class="sxs-lookup"><span data-stu-id="9de51-121">Value</span></span>|<span data-ttu-id="9de51-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9de51-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="9de51-123">Keine</span><span class="sxs-lookup"><span data-stu-id="9de51-123">None</span></span>|<span data-ttu-id="9de51-124">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="9de51-124">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="9de51-125">Transport</span><span class="sxs-lookup"><span data-stu-id="9de51-125">Transport</span></span>|<span data-ttu-id="9de51-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9de51-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="9de51-127">Die SOAP-Nachrichten werden über HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="9de51-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="9de51-128">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9de51-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="9de51-129">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9de51-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="9de51-130">Meldung</span><span class="sxs-lookup"><span data-stu-id="9de51-130">Message</span></span>|<span data-ttu-id="9de51-131">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9de51-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="9de51-132">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="9de51-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="9de51-133">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9de51-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="9de51-134">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="9de51-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="9de51-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9de51-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="9de51-136">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9de51-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="9de51-137">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9de51-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="9de51-138">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9de51-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="9de51-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9de51-139">TransportCredentialOnly</span></span>|<span data-ttu-id="9de51-140">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="9de51-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9de51-141">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9de51-141">It provides http-based client authentication.</span></span> <span data-ttu-id="9de51-142">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de51-142">This mode should be used with caution.</span></span> <span data-ttu-id="9de51-143">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit durch andere Mittel (z. B. IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9de51-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9de51-144">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9de51-144">Child elements</span></span>

|<span data-ttu-id="9de51-145">Element</span><span class="sxs-lookup"><span data-stu-id="9de51-145">Element</span></span>|<span data-ttu-id="9de51-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9de51-146">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9de51-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="9de51-147">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="9de51-148">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="9de51-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="9de51-149">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="9de51-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="9de51-150">\<message></span><span class="sxs-lookup"><span data-stu-id="9de51-150">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="9de51-151">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="9de51-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="9de51-152">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="9de51-152">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9de51-153">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9de51-153">Parent elements</span></span>

|<span data-ttu-id="9de51-154">Element</span><span class="sxs-lookup"><span data-stu-id="9de51-154">Element</span></span>|<span data-ttu-id="9de51-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9de51-155">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="9de51-156">Bindung</span><span class="sxs-lookup"><span data-stu-id="9de51-156">binding</span></span>|<span data-ttu-id="9de51-157">Das Bindungselement, das von der [ \<BasicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9de51-157">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="9de51-158">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9de51-158">Remarks</span></span>

 <span data-ttu-id="9de51-159">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9de51-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="9de51-160">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `netHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9de51-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="9de51-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9de51-161">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="9de51-162">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="9de51-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9de51-163">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="9de51-163">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="9de51-164">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9de51-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9de51-165">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9de51-165">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9de51-166">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9de51-166">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9de51-167">\<binding></span><span class="sxs-lookup"><span data-stu-id="9de51-167">\<binding></span></span>](../../../misc/binding.md)
