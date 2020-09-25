---
title: <peerAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 7e4f86c361dc3ade5dedf4017921516357bb9a58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181582"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="4da1e-102">\<peerAuthentication>-Element</span><span class="sxs-lookup"><span data-stu-id="4da1e-102">\<peerAuthentication> Element</span></span>

<span data-ttu-id="4da1e-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="4da1e-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="4da1e-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="4da1e-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="4da1e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4da1e-105">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4da1e-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4da1e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4da1e-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4da1e-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4da1e-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="4da1e-108">Attributes</span></span>  
  
|<span data-ttu-id="4da1e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="4da1e-109">Attribute</span></span>|<span data-ttu-id="4da1e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da1e-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="4da1e-111">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4da1e-111">Optional string.</span></span> <span data-ttu-id="4da1e-112">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4da1e-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="4da1e-113">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4da1e-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="4da1e-114">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4da1e-114">Optional enumeration.</span></span> <span data-ttu-id="4da1e-115">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="4da1e-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="4da1e-116">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4da1e-116">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="4da1e-117">Der Standardwert ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-117">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="4da1e-118">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4da1e-118">Optional enumeration.</span></span> <span data-ttu-id="4da1e-119">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="4da1e-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="4da1e-120">Der Standardwert lautet `Online`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-120">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="4da1e-121">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4da1e-121">Optional enumeration.</span></span> <span data-ttu-id="4da1e-122">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4da1e-123">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="4da1e-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="4da1e-124">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4da1e-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="4da1e-125">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="4da1e-126">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="4da1e-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="4da1e-127">Wert</span><span class="sxs-lookup"><span data-stu-id="4da1e-127">Value</span></span>|<span data-ttu-id="4da1e-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4da1e-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4da1e-129">String</span><span class="sxs-lookup"><span data-stu-id="4da1e-129">String</span></span>|<span data-ttu-id="4da1e-130">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="4da1e-130">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="4da1e-131">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4da1e-131">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="4da1e-132">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="4da1e-132">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="4da1e-133">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="4da1e-133">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="4da1e-134">Wert</span><span class="sxs-lookup"><span data-stu-id="4da1e-134">Value</span></span>|<span data-ttu-id="4da1e-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da1e-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4da1e-136">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4da1e-136">Enumeration</span></span>|<span data-ttu-id="4da1e-137">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-137">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="4da1e-138">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-138">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="4da1e-139">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4da1e-139">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="4da1e-140">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="4da1e-140">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="4da1e-141">Wert</span><span class="sxs-lookup"><span data-stu-id="4da1e-141">Value</span></span>|<span data-ttu-id="4da1e-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da1e-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4da1e-143">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4da1e-143">Enumeration</span></span>|<span data-ttu-id="4da1e-144">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-144">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="4da1e-145">Der Standardwert lautet `Online`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-145">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="4da1e-146">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4da1e-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="4da1e-147">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="4da1e-147">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="4da1e-148">Wert</span><span class="sxs-lookup"><span data-stu-id="4da1e-148">Value</span></span>|<span data-ttu-id="4da1e-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da1e-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4da1e-150">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4da1e-150">Enumeration</span></span>|<span data-ttu-id="4da1e-151">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-151">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4da1e-152">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-152">The default is `CurrentUser`.</span></span> <span data-ttu-id="4da1e-153">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-153">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="4da1e-154">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4da1e-154">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4da1e-155">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4da1e-155">Child Elements</span></span>  

 <span data-ttu-id="4da1e-156">Keine</span><span class="sxs-lookup"><span data-stu-id="4da1e-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4da1e-157">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4da1e-157">Parent Elements</span></span>  
  
|<span data-ttu-id="4da1e-158">Element</span><span class="sxs-lookup"><span data-stu-id="4da1e-158">Element</span></span>|<span data-ttu-id="4da1e-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4da1e-159">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="4da1e-160">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4da1e-160">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4da1e-161">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4da1e-161">Remarks</span></span>  

 <span data-ttu-id="4da1e-162">Das `<authentication>`-Element entspricht der <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4da1e-162">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="4da1e-163">Mit diesem Element wird ein Validierungssteuerelement angegeben, das bei Nachbar-zu-Nachbar-Authentifizierung im Mesh aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4da1e-163">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="4da1e-164">Versucht ein neuer Peer, eine Nachbarverbindung herzustellen, übergibt er seine eigenen Anmeldeinformationen an den antwortenden Peer.</span><span class="sxs-lookup"><span data-stu-id="4da1e-164">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="4da1e-165">Das Validierungssteuerelement des antwortenden Peers wird aufgerufen, um die Anmeldeinformationen der Remotepartei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4da1e-165">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="4da1e-166">Bei jeder Herstellung einer Peerverbindung im Mesh werden beide Peers gegenseitig authentifziert, das heißt, die Validierungssteuerelemente werden an beiden Enden aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4da1e-166">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da1e-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4da1e-167">Example</span></span>  

 <span data-ttu-id="4da1e-168">Mit dem folgenden Code wird der Zertifikatprüfmodus auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4da1e-168">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4da1e-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4da1e-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="4da1e-170">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="4da1e-170">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4da1e-171">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="4da1e-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="4da1e-172">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4da1e-172">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="4da1e-173">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4da1e-173">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="4da1e-174">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="4da1e-174">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
