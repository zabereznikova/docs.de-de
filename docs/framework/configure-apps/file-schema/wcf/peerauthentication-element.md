---
title: '&lt;peerAuthentication&gt;-Element'
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 0491a175c237bf6dd18b607d8ad99f1057661d76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610018"
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="e75fd-102">&lt;peerAuthentication&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="e75fd-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="e75fd-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="e75fd-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="e75fd-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="e75fd-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="e75fd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e75fd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e75fd-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e75fd-106">\<behaviors></span></span>  
<span data-ttu-id="e75fd-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e75fd-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="e75fd-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e75fd-108">\<behavior></span></span>  
<span data-ttu-id="e75fd-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e75fd-109">\<clientCredentials></span></span>  
<span data-ttu-id="e75fd-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="e75fd-110">\<peer></span></span>  
<span data-ttu-id="e75fd-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e75fd-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75fd-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="e75fd-112">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e75fd-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e75fd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e75fd-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e75fd-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e75fd-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="e75fd-115">Attributes</span></span>  
  
|<span data-ttu-id="e75fd-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="e75fd-116">Attribute</span></span>|<span data-ttu-id="e75fd-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75fd-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="e75fd-118">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e75fd-118">Optional string.</span></span> <span data-ttu-id="e75fd-119">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e75fd-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="e75fd-120">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e75fd-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="e75fd-121">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e75fd-121">Optional enumeration.</span></span> <span data-ttu-id="e75fd-122">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="e75fd-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="e75fd-123">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e75fd-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="e75fd-124">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="e75fd-125">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e75fd-125">Optional enumeration.</span></span> <span data-ttu-id="e75fd-126">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="e75fd-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="e75fd-127">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="e75fd-128">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e75fd-128">Optional enumeration.</span></span> <span data-ttu-id="e75fd-129">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e75fd-130">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="e75fd-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="e75fd-131">Validierung wird ausgeführt, für die **vertrauenswürdige Personen** am angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e75fd-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="e75fd-132">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="e75fd-133">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="e75fd-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="e75fd-134">Wert</span><span class="sxs-lookup"><span data-stu-id="e75fd-134">Value</span></span>|<span data-ttu-id="e75fd-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75fd-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e75fd-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e75fd-136">String</span></span>|<span data-ttu-id="e75fd-137">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="e75fd-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="e75fd-138">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e75fd-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="e75fd-139">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="e75fd-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="e75fd-140">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e75fd-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="e75fd-141">Wert</span><span class="sxs-lookup"><span data-stu-id="e75fd-141">Value</span></span>|<span data-ttu-id="e75fd-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75fd-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e75fd-143">Enumeration</span><span class="sxs-lookup"><span data-stu-id="e75fd-143">Enumeration</span></span>|<span data-ttu-id="e75fd-144">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="e75fd-145">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="e75fd-146">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e75fd-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="e75fd-147">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e75fd-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="e75fd-148">Wert</span><span class="sxs-lookup"><span data-stu-id="e75fd-148">Value</span></span>|<span data-ttu-id="e75fd-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75fd-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e75fd-150">Enumeration</span><span class="sxs-lookup"><span data-stu-id="e75fd-150">Enumeration</span></span>|<span data-ttu-id="e75fd-151">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="e75fd-152">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="e75fd-153">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e75fd-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="e75fd-154">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="e75fd-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="e75fd-155">Wert</span><span class="sxs-lookup"><span data-stu-id="e75fd-155">Value</span></span>|<span data-ttu-id="e75fd-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75fd-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e75fd-157">Enumeration</span><span class="sxs-lookup"><span data-stu-id="e75fd-157">Enumeration</span></span>|<span data-ttu-id="e75fd-158">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e75fd-159">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="e75fd-160">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="e75fd-161">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e75fd-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e75fd-162">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e75fd-162">Child Elements</span></span>  
 <span data-ttu-id="e75fd-163">Keine</span><span class="sxs-lookup"><span data-stu-id="e75fd-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e75fd-164">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e75fd-164">Parent Elements</span></span>  
  
|<span data-ttu-id="e75fd-165">Element</span><span class="sxs-lookup"><span data-stu-id="e75fd-165">Element</span></span>|<span data-ttu-id="e75fd-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75fd-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e75fd-167">\<peer></span><span class="sxs-lookup"><span data-stu-id="e75fd-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="e75fd-168">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e75fd-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e75fd-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e75fd-169">Remarks</span></span>  
 <span data-ttu-id="e75fd-170">Das `<authentication>`-Element entspricht der <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e75fd-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="e75fd-171">Mit diesem Element wird ein Validierungssteuerelement angegeben, das bei Nachbar-zu-Nachbar-Authentifizierung im Mesh aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e75fd-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="e75fd-172">Versucht ein neuer Peer, eine Nachbarverbindung herzustellen, übergibt er seine eigenen Anmeldeinformationen an den antwortenden Peer.</span><span class="sxs-lookup"><span data-stu-id="e75fd-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="e75fd-173">Das Validierungssteuerelement des antwortenden Peers wird aufgerufen, um die Anmeldeinformationen der Remotepartei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e75fd-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="e75fd-174">Bei jeder Herstellung einer Peerverbindung im Mesh werden beide Peers gegenseitig authentifziert, das heißt, die Validierungssteuerelemente werden an beiden Enden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e75fd-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e75fd-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e75fd-175">Example</span></span>  
 <span data-ttu-id="e75fd-176">Mit dem folgenden Code wird der Zertifikatvalidierungsmodus auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e75fd-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="e75fd-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e75fd-177">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="e75fd-178">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="e75fd-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e75fd-179">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="e75fd-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="e75fd-180">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="e75fd-180">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="e75fd-181">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e75fd-181">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="e75fd-182">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="e75fd-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
