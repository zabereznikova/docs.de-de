---
title: '&lt;certificate&gt;-Element'
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 5329fb276766ca2bd24f0fd3aef793fbb3b1f8b8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43397993"
---
# <a name="ltcertificategt-element"></a><span data-ttu-id="99c94-102">&lt;certificate&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="99c94-102">&lt;certificate&gt; Element</span></span>
<span data-ttu-id="99c94-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99c94-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="99c94-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="99c94-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99c94-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="99c94-105">\<behaviors></span></span>  
<span data-ttu-id="99c94-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="99c94-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="99c94-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="99c94-107">\<behavior></span></span>  
<span data-ttu-id="99c94-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="99c94-108">\<clientCredentials></span></span>  
<span data-ttu-id="99c94-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="99c94-109">\<peer></span></span>  
<span data-ttu-id="99c94-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="99c94-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c94-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="99c94-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c94-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99c94-112">Attributes and Elements</span></span>  
 <span data-ttu-id="99c94-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99c94-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c94-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="99c94-114">Attributes</span></span>  
  
|<span data-ttu-id="99c94-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="99c94-115">Attribute</span></span>|<span data-ttu-id="99c94-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99c94-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="99c94-117">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="99c94-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="99c94-118">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="99c94-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="99c94-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="99c94-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="99c94-120">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="99c94-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="99c94-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="99c94-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99c94-122">-LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="99c94-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="99c94-123">-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="99c94-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="99c94-124">Die Standardeinstellung ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="99c94-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="99c94-125">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99c94-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="99c94-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="99c94-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99c94-127">-AddressBook: Zertifikatspeicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="99c94-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="99c94-128">-AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="99c94-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="99c94-129">-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen-Zertifikate (CAs).</span><span class="sxs-lookup"><span data-stu-id="99c94-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="99c94-130">– Nicht zulässig: Der Zertifikatspeicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="99c94-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="99c94-131">– My: Der Zertifikatspeicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="99c94-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="99c94-132">-Root: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="99c94-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="99c94-133">– TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="99c94-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="99c94-134">-TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="99c94-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="99c94-135">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="99c94-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="99c94-136">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="99c94-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="99c94-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="99c94-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99c94-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="99c94-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="99c94-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="99c94-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="99c94-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="99c94-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="99c94-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="99c94-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="99c94-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="99c94-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="99c94-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="99c94-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="99c94-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="99c94-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="99c94-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="99c94-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="99c94-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="99c94-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="99c94-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="99c94-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="99c94-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="99c94-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="99c94-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="99c94-149">-   FindByExtension</span></span><br /><span data-ttu-id="99c94-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="99c94-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="99c94-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="99c94-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="99c94-152">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="99c94-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="99c94-153">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="99c94-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c94-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99c94-154">Child Elements</span></span>  
 <span data-ttu-id="99c94-155">Keine</span><span class="sxs-lookup"><span data-stu-id="99c94-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99c94-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99c94-156">Parent Elements</span></span>  
  
|<span data-ttu-id="99c94-157">Element</span><span class="sxs-lookup"><span data-stu-id="99c94-157">Element</span></span>|<span data-ttu-id="99c94-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99c94-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99c94-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="99c94-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="99c94-160">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99c94-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c94-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99c94-161">Remarks</span></span>  
 <span data-ttu-id="99c94-162">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="99c94-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="99c94-163">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="99c94-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c94-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99c94-164">Example</span></span>  
 <span data-ttu-id="99c94-165">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="99c94-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="99c94-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99c94-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 [<span data-ttu-id="99c94-167">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="99c94-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="99c94-168">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="99c94-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="99c94-169">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="99c94-169">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="99c94-170">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="99c94-170">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="99c94-171">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="99c94-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
