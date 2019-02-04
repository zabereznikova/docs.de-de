---
title: <certificate>-Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: f0cec2ad0e7747ddbc0ef566b4e8cbc7f8795b02
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675386"
---
# <a name="certificate-element"></a><span data-ttu-id="0a27b-102">\<Zertifikat >-Element</span><span class="sxs-lookup"><span data-stu-id="0a27b-102">\<certificate> Element</span></span>
<span data-ttu-id="0a27b-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0a27b-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="0a27b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0a27b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a27b-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0a27b-105">\<behaviors></span></span>  
<span data-ttu-id="0a27b-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0a27b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0a27b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0a27b-107">\<behavior></span></span>  
<span data-ttu-id="0a27b-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0a27b-108">\<clientCredentials></span></span>  
<span data-ttu-id="0a27b-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="0a27b-109">\<peer></span></span>  
<span data-ttu-id="0a27b-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="0a27b-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a27b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a27b-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a27b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a27b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0a27b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a27b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a27b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a27b-114">Attributes</span></span>  
  
|<span data-ttu-id="0a27b-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="0a27b-115">Attribute</span></span>|<span data-ttu-id="0a27b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a27b-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="0a27b-117">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a27b-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="0a27b-118">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0a27b-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="0a27b-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0a27b-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="0a27b-120">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a27b-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="0a27b-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0a27b-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0a27b-122">-LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="0a27b-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="0a27b-123">-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="0a27b-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="0a27b-124">Die Standardeinstellung ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0a27b-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="0a27b-125">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a27b-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="0a27b-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0a27b-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0a27b-127">-AddressBook: Der Zertifikatspeicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0a27b-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="0a27b-128">-   AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="0a27b-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="0a27b-129">-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen-Zertifikate (CAs).</span><span class="sxs-lookup"><span data-stu-id="0a27b-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="0a27b-130">– Nicht zulässig: Der Zertifikatspeicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="0a27b-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="0a27b-131">-Meine: Der Zertifikatspeicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="0a27b-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="0a27b-132">-Stammverzeichnis: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="0a27b-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="0a27b-133">– TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0a27b-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="0a27b-134">-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="0a27b-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="0a27b-135">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="0a27b-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="0a27b-136">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a27b-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="0a27b-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0a27b-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0a27b-138">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="0a27b-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="0a27b-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="0a27b-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="0a27b-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0a27b-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="0a27b-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="0a27b-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="0a27b-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0a27b-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="0a27b-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="0a27b-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="0a27b-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="0a27b-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="0a27b-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="0a27b-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="0a27b-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="0a27b-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="0a27b-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="0a27b-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="0a27b-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="0a27b-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="0a27b-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="0a27b-149">-   FindByExtension</span></span><br /><span data-ttu-id="0a27b-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="0a27b-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="0a27b-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="0a27b-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="0a27b-152">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0a27b-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="0a27b-153">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="0a27b-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a27b-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a27b-154">Child Elements</span></span>  
 <span data-ttu-id="0a27b-155">Keine</span><span class="sxs-lookup"><span data-stu-id="0a27b-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a27b-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a27b-156">Parent Elements</span></span>  
  
|<span data-ttu-id="0a27b-157">Element</span><span class="sxs-lookup"><span data-stu-id="0a27b-157">Element</span></span>|<span data-ttu-id="0a27b-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a27b-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a27b-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="0a27b-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="0a27b-160">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a27b-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a27b-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a27b-161">Remarks</span></span>  
 <span data-ttu-id="0a27b-162">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0a27b-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="0a27b-163">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="0a27b-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a27b-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a27b-164">Example</span></span>  
 <span data-ttu-id="0a27b-165">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="0a27b-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="0a27b-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a27b-166">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="0a27b-167">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="0a27b-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0a27b-168">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="0a27b-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="0a27b-169">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0a27b-169">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="0a27b-170">[Benutzerdefinierter Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0a27b-170">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="0a27b-171">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="0a27b-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
