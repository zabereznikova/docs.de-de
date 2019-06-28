---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 804c280bcdb0fecc87f71121b7d95b5fd0268de9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423120"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="a0988-102">\<MessageSenderAuthentication >-Element</span><span class="sxs-lookup"><span data-stu-id="a0988-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="a0988-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="a0988-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="a0988-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="a0988-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="a0988-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a0988-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0988-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a0988-106">\<behaviors></span></span>  
<span data-ttu-id="a0988-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a0988-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="a0988-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a0988-108">\<behavior></span></span>  
<span data-ttu-id="a0988-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a0988-109">\<clientCredentials></span></span>  
<span data-ttu-id="a0988-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="a0988-110">\<peer></span></span>  
<span data-ttu-id="a0988-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="a0988-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0988-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0988-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0988-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0988-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a0988-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0988-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0988-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0988-115">Attributes</span></span>  
  
|<span data-ttu-id="a0988-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0988-116">Attribute</span></span>|<span data-ttu-id="a0988-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0988-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="a0988-118">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0988-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a0988-119">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a0988-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="a0988-120">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="a0988-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a0988-121">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a0988-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="a0988-122">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a0988-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="a0988-123">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0988-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a0988-124">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="a0988-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="a0988-125">Validierung wird ausgeführt, für die **vertrauenswürdige Personen** am angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a0988-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="a0988-126">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0988-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="a0988-127">Wert</span><span class="sxs-lookup"><span data-stu-id="a0988-127">Value</span></span>|<span data-ttu-id="a0988-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0988-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0988-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a0988-129">String</span></span>|<span data-ttu-id="a0988-130">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a0988-130">Optional.</span></span> <span data-ttu-id="a0988-131">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="a0988-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="a0988-132">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a0988-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="a0988-133">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="a0988-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="a0988-134">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0988-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="a0988-135">Wert</span><span class="sxs-lookup"><span data-stu-id="a0988-135">Value</span></span>|<span data-ttu-id="a0988-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0988-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0988-137">Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0988-137">Enumeration</span></span>|<span data-ttu-id="a0988-138">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a0988-138">Optional.</span></span> <span data-ttu-id="a0988-139">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a0988-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="a0988-140">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a0988-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="a0988-141">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a0988-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="a0988-142">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a0988-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="a0988-143">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0988-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="a0988-144">Wert</span><span class="sxs-lookup"><span data-stu-id="a0988-144">Value</span></span>|<span data-ttu-id="a0988-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0988-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0988-146">Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0988-146">Enumeration</span></span>|<span data-ttu-id="a0988-147">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="a0988-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="a0988-148">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="a0988-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="a0988-149">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a0988-149">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="a0988-150">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0988-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="a0988-151">Wert</span><span class="sxs-lookup"><span data-stu-id="a0988-151">Value</span></span>|<span data-ttu-id="a0988-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0988-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0988-153">Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0988-153">Enumeration</span></span>|<span data-ttu-id="a0988-154">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0988-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a0988-155">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0988-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="a0988-156">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="a0988-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="a0988-157">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0988-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="a0988-158">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0988-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0988-159">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0988-159">Child Elements</span></span>  
 <span data-ttu-id="a0988-160">Keine</span><span class="sxs-lookup"><span data-stu-id="a0988-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0988-161">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0988-161">Parent Elements</span></span>  
  
|<span data-ttu-id="a0988-162">Element</span><span class="sxs-lookup"><span data-stu-id="a0988-162">Element</span></span>|<span data-ttu-id="a0988-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0988-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0988-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="a0988-164">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="a0988-165">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0988-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0988-166">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0988-166">Remarks</span></span>  
 <span data-ttu-id="a0988-167">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="a0988-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="a0988-168">Für Ausgabekanäle wird jede Nachricht ist signiert unter Verwendung des Zertifikats von bereitgestellten [ \<Zertifikat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="a0988-168">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="a0988-169">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="a0988-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="a0988-170">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="a0988-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0988-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0988-171">Example</span></span>  
 <span data-ttu-id="a0988-172">Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a0988-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0988-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0988-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="a0988-174">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="a0988-174">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a0988-175">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="a0988-175">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="a0988-176">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a0988-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="a0988-177">[Benutzerdefinierter Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a0988-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="a0988-178">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="a0988-178">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
