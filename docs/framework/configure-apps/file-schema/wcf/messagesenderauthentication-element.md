---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 410fffd541926b9a2e75c04d26a2a1e08a262939
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764087"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="ba10e-102">\<MessageSenderAuthentication >-Element</span><span class="sxs-lookup"><span data-stu-id="ba10e-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="ba10e-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="ba10e-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="ba10e-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="ba10e-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="ba10e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba10e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba10e-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ba10e-106">\<behaviors></span></span>  
<span data-ttu-id="ba10e-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ba10e-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="ba10e-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba10e-108">\<behavior></span></span>  
<span data-ttu-id="ba10e-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ba10e-109">\<clientCredentials></span></span>  
<span data-ttu-id="ba10e-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="ba10e-110">\<peer></span></span>  
<span data-ttu-id="ba10e-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="ba10e-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba10e-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba10e-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba10e-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba10e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ba10e-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba10e-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba10e-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba10e-115">Attributes</span></span>  
  
|<span data-ttu-id="ba10e-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba10e-116">Attribute</span></span>|<span data-ttu-id="ba10e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba10e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba10e-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="ba10e-118">customCertificateValidatorType</span></span>|<span data-ttu-id="ba10e-119">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba10e-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ba10e-120">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba10e-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="ba10e-121">certifcateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ba10e-121">certifcateValidationMode</span></span>|<span data-ttu-id="ba10e-122">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="ba10e-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="ba10e-123">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ba10e-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="ba10e-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ba10e-124">revocationMode</span></span>|<span data-ttu-id="ba10e-125">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="ba10e-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="ba10e-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ba10e-126">trustedStoreLocation</span></span>|<span data-ttu-id="ba10e-127">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ba10e-128">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="ba10e-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="ba10e-129">Validierung wird ausgeführt, für die **vertrauenswürdige Personen** am angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ba10e-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="ba10e-130">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="ba10e-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="ba10e-131">Wert</span><span class="sxs-lookup"><span data-stu-id="ba10e-131">Value</span></span>|<span data-ttu-id="ba10e-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba10e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba10e-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ba10e-133">String</span></span>|<span data-ttu-id="ba10e-134">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ba10e-134">Optional.</span></span> <span data-ttu-id="ba10e-135">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="ba10e-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="ba10e-136">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ba10e-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="ba10e-137">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="ba10e-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="ba10e-138">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="ba10e-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="ba10e-139">Wert</span><span class="sxs-lookup"><span data-stu-id="ba10e-139">Value</span></span>|<span data-ttu-id="ba10e-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba10e-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba10e-141">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ba10e-141">Enumeration</span></span>|<span data-ttu-id="ba10e-142">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ba10e-142">Optional.</span></span> <span data-ttu-id="ba10e-143">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="ba10e-144">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="ba10e-145">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="ba10e-146">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="ba10e-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="ba10e-147">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="ba10e-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="ba10e-148">Wert</span><span class="sxs-lookup"><span data-stu-id="ba10e-148">Value</span></span>|<span data-ttu-id="ba10e-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba10e-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba10e-150">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ba10e-150">Enumeration</span></span>|<span data-ttu-id="ba10e-151">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="ba10e-152">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="ba10e-153">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="ba10e-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="ba10e-154">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="ba10e-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="ba10e-155">Wert</span><span class="sxs-lookup"><span data-stu-id="ba10e-155">Value</span></span>|<span data-ttu-id="ba10e-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba10e-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba10e-157">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ba10e-157">Enumeration</span></span>|<span data-ttu-id="ba10e-158">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ba10e-159">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="ba10e-160">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="ba10e-161">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="ba10e-162">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ba10e-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba10e-163">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba10e-163">Child Elements</span></span>  
 <span data-ttu-id="ba10e-164">Keine</span><span class="sxs-lookup"><span data-stu-id="ba10e-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba10e-165">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba10e-165">Parent Elements</span></span>  
  
|<span data-ttu-id="ba10e-166">Element</span><span class="sxs-lookup"><span data-stu-id="ba10e-166">Element</span></span>|<span data-ttu-id="ba10e-167">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba10e-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba10e-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="ba10e-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="ba10e-169">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba10e-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba10e-170">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba10e-170">Remarks</span></span>  
 <span data-ttu-id="ba10e-171">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ba10e-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="ba10e-172">Für Ausgabekanäle wird jede Nachricht ist signiert unter Verwendung des Zertifikats von bereitgestellten [ \<Zertifikat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="ba10e-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="ba10e-173">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="ba10e-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="ba10e-174">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="ba10e-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba10e-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba10e-175">Example</span></span>  
 <span data-ttu-id="ba10e-176">Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ba10e-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="ba10e-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba10e-177">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="ba10e-178">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="ba10e-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ba10e-179">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="ba10e-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="ba10e-180">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ba10e-180">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="ba10e-181">[Benutzerdefinierter Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ba10e-181">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="ba10e-182">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="ba10e-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
