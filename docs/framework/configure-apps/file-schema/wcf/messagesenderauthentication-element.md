---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 1e63b6fa93e1abfa87c83da4b5d46f492c59b9bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931377"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="5b177-102">\<messagesenderauthentication-> Element</span><span class="sxs-lookup"><span data-stu-id="5b177-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="5b177-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="5b177-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="5b177-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="5b177-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="5b177-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5b177-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b177-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5b177-106">\<behaviors></span></span>  
<span data-ttu-id="5b177-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5b177-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="5b177-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5b177-108">\<behavior></span></span>  
<span data-ttu-id="5b177-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5b177-109">\<clientCredentials></span></span>  
<span data-ttu-id="5b177-110">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="5b177-110">\<peer></span></span>  
<span data-ttu-id="5b177-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="5b177-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b177-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b177-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b177-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5b177-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5b177-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b177-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b177-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="5b177-115">Attributes</span></span>  
  
|<span data-ttu-id="5b177-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="5b177-116">Attribute</span></span>|<span data-ttu-id="5b177-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b177-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="5b177-118">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b177-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="5b177-119">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b177-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="5b177-120">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="5b177-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="5b177-121">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5b177-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="5b177-122">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="5b177-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="5b177-123">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5b177-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="5b177-124">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="5b177-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="5b177-125">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5b177-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="5b177-126">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="5b177-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="5b177-127">Wert</span><span class="sxs-lookup"><span data-stu-id="5b177-127">Value</span></span>|<span data-ttu-id="5b177-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b177-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b177-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b177-129">String</span></span>|<span data-ttu-id="5b177-130">Optional.</span><span class="sxs-lookup"><span data-stu-id="5b177-130">Optional.</span></span> <span data-ttu-id="5b177-131">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="5b177-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="5b177-132">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b177-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="5b177-133">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="5b177-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="5b177-134">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="5b177-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="5b177-135">Wert</span><span class="sxs-lookup"><span data-stu-id="5b177-135">Value</span></span>|<span data-ttu-id="5b177-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b177-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b177-137">Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b177-137">Enumeration</span></span>|<span data-ttu-id="5b177-138">Optional.</span><span class="sxs-lookup"><span data-stu-id="5b177-138">Optional.</span></span> <span data-ttu-id="5b177-139">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="5b177-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="5b177-140">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5b177-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="5b177-141">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5b177-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="5b177-142">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5b177-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="5b177-143">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="5b177-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="5b177-144">Wert</span><span class="sxs-lookup"><span data-stu-id="5b177-144">Value</span></span>|<span data-ttu-id="5b177-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b177-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b177-146">Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b177-146">Enumeration</span></span>|<span data-ttu-id="5b177-147">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="5b177-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="5b177-148">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="5b177-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="5b177-149">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5b177-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="5b177-150">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="5b177-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="5b177-151">Wert</span><span class="sxs-lookup"><span data-stu-id="5b177-151">Value</span></span>|<span data-ttu-id="5b177-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b177-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b177-153">Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b177-153">Enumeration</span></span>|<span data-ttu-id="5b177-154">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5b177-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="5b177-155">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5b177-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="5b177-156">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="5b177-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="5b177-157">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5b177-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="5b177-158">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5b177-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b177-159">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b177-159">Child Elements</span></span>  
 <span data-ttu-id="5b177-160">Keine</span><span class="sxs-lookup"><span data-stu-id="5b177-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b177-161">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b177-161">Parent Elements</span></span>  
  
|<span data-ttu-id="5b177-162">Element</span><span class="sxs-lookup"><span data-stu-id="5b177-162">Element</span></span>|<span data-ttu-id="5b177-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b177-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b177-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="5b177-164">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="5b177-165">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b177-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b177-166">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b177-166">Remarks</span></span>  
 <span data-ttu-id="5b177-167">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="5b177-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="5b177-168">Für Ausgabekanäle wird jede Nachricht mit dem Zertifikat signiert, das von [ \<Certificate >](certificate-element.md)bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5b177-168">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="5b177-169">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="5b177-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="5b177-170">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="5b177-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b177-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b177-171">Example</span></span>  
 <span data-ttu-id="5b177-172">Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5b177-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5b177-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b177-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="5b177-174">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="5b177-174">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5b177-175">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="5b177-175">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="5b177-176">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5b177-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="5b177-177">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5b177-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="5b177-178">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="5b177-178">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
