---
title: <peerAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400086"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="cf817-102">\<> Element "Peer Authentication"</span><span class="sxs-lookup"><span data-stu-id="cf817-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="cf817-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="cf817-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="cf817-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="cf817-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="cf817-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cf817-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cf817-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="cf817-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="cf817-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="cf817-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="cf817-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Peer >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf817-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="cf817-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> "Peer Authentifizierung"**</span><span class="sxs-lookup"><span data-stu-id="cf817-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf817-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf817-113">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf817-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf817-114">Attributes and Elements</span></span>  
 <span data-ttu-id="cf817-115">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf817-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf817-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf817-116">Attributes</span></span>  
  
|<span data-ttu-id="cf817-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="cf817-117">Attribute</span></span>|<span data-ttu-id="cf817-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf817-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="cf817-119">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cf817-119">Optional string.</span></span> <span data-ttu-id="cf817-120">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf817-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="cf817-121">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="cf817-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="cf817-122">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="cf817-122">Optional enumeration.</span></span> <span data-ttu-id="cf817-123">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="cf817-123">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="cf817-124">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cf817-124">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="cf817-125">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="cf817-125">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="cf817-126">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="cf817-126">Optional enumeration.</span></span> <span data-ttu-id="cf817-127">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="cf817-127">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="cf817-128">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="cf817-128">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="cf817-129">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="cf817-129">Optional enumeration.</span></span> <span data-ttu-id="cf817-130">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="cf817-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="cf817-131">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="cf817-131">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="cf817-132">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf817-132">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="cf817-133">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="cf817-133">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="cf817-134">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="cf817-134">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="cf817-135">Wert</span><span class="sxs-lookup"><span data-stu-id="cf817-135">Value</span></span>|<span data-ttu-id="cf817-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf817-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf817-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="cf817-137">String</span></span>|<span data-ttu-id="cf817-138">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="cf817-138">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="cf817-139">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cf817-139">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="cf817-140">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="cf817-140">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="cf817-141">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="cf817-141">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="cf817-142">Wert</span><span class="sxs-lookup"><span data-stu-id="cf817-142">Value</span></span>|<span data-ttu-id="cf817-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf817-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf817-144">Enumeration</span><span class="sxs-lookup"><span data-stu-id="cf817-144">Enumeration</span></span>|<span data-ttu-id="cf817-145">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="cf817-145">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="cf817-146">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="cf817-146">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="cf817-147">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="cf817-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="cf817-148">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="cf817-148">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="cf817-149">Wert</span><span class="sxs-lookup"><span data-stu-id="cf817-149">Value</span></span>|<span data-ttu-id="cf817-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf817-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf817-151">Enumeration</span><span class="sxs-lookup"><span data-stu-id="cf817-151">Enumeration</span></span>|<span data-ttu-id="cf817-152">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="cf817-152">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="cf817-153">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="cf817-153">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="cf817-154">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="cf817-154">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="cf817-155">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="cf817-155">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="cf817-156">Wert</span><span class="sxs-lookup"><span data-stu-id="cf817-156">Value</span></span>|<span data-ttu-id="cf817-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf817-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf817-158">Enumeration</span><span class="sxs-lookup"><span data-stu-id="cf817-158">Enumeration</span></span>|<span data-ttu-id="cf817-159">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="cf817-159">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="cf817-160">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="cf817-160">The default is `CurrentUser`.</span></span> <span data-ttu-id="cf817-161">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="cf817-161">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="cf817-162">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="cf817-162">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf817-163">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf817-163">Child Elements</span></span>  
 <span data-ttu-id="cf817-164">Keine</span><span class="sxs-lookup"><span data-stu-id="cf817-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf817-165">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf817-165">Parent Elements</span></span>  
  
|<span data-ttu-id="cf817-166">Element</span><span class="sxs-lookup"><span data-stu-id="cf817-166">Element</span></span>|<span data-ttu-id="cf817-167">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf817-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf817-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="cf817-168">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="cf817-169">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf817-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf817-170">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf817-170">Remarks</span></span>  
 <span data-ttu-id="cf817-171">Das `<authentication>`-Element entspricht der <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf817-171">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="cf817-172">Mit diesem Element wird ein Validierungssteuerelement angegeben, das bei Nachbar-zu-Nachbar-Authentifizierung im Mesh aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cf817-172">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="cf817-173">Versucht ein neuer Peer, eine Nachbarverbindung herzustellen, übergibt er seine eigenen Anmeldeinformationen an den antwortenden Peer.</span><span class="sxs-lookup"><span data-stu-id="cf817-173">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="cf817-174">Das Validierungssteuerelement des antwortenden Peers wird aufgerufen, um die Anmeldeinformationen der Remotepartei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cf817-174">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="cf817-175">Bei jeder Herstellung einer Peerverbindung im Mesh werden beide Peers gegenseitig authentifziert, das heißt, die Validierungssteuerelemente werden an beiden Enden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cf817-175">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf817-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf817-176">Example</span></span>  
 <span data-ttu-id="cf817-177">Mit dem folgenden Code wird der Zertifikatprüfmodus auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cf817-177">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf817-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf817-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="cf817-179">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cf817-179">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="cf817-180">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="cf817-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="cf817-181">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cf817-181">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="cf817-182">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cf817-182">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="cf817-183">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="cf817-183">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
