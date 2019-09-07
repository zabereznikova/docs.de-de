---
title: <certificate>-Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400556"
---
# <a name="certificate-element"></a><span data-ttu-id="58e1b-102">\<Certificate >-Element</span><span class="sxs-lookup"><span data-stu-id="58e1b-102">\<certificate> Element</span></span>
<span data-ttu-id="58e1b-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58e1b-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="58e1b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58e1b-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="58e1b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="58e1b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="58e1b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="58e1b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="58e1b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Peer >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="58e1b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="58e1b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Zertifikat >**</span><span class="sxs-lookup"><span data-stu-id="58e1b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e1b-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="58e1b-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58e1b-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58e1b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="58e1b-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58e1b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58e1b-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="58e1b-115">Attributes</span></span>  
  
|<span data-ttu-id="58e1b-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="58e1b-116">Attribute</span></span>|<span data-ttu-id="58e1b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58e1b-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="58e1b-118">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="58e1b-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="58e1b-119">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="58e1b-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="58e1b-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="58e1b-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="58e1b-121">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="58e1b-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="58e1b-122">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="58e1b-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="58e1b-123">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="58e1b-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="58e1b-124">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="58e1b-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="58e1b-125">Die Standardeinstellung ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="58e1b-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="58e1b-126">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="58e1b-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="58e1b-127">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="58e1b-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="58e1b-128">AddressBook Der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="58e1b-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="58e1b-129">AuthRoot Der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="58e1b-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="58e1b-130">CertificateAuthority Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="58e1b-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="58e1b-131">Nicht zulässig Der Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="58e1b-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="58e1b-132">Danken Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="58e1b-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="58e1b-133">Fasst Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen (CAS).</span><span class="sxs-lookup"><span data-stu-id="58e1b-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="58e1b-134">TrustedPeople Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="58e1b-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="58e1b-135">TrustedPublisher Der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="58e1b-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="58e1b-136">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="58e1b-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="58e1b-137">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="58e1b-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="58e1b-138">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="58e1b-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="58e1b-139">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="58e1b-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="58e1b-140">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="58e1b-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="58e1b-141">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="58e1b-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="58e1b-142">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="58e1b-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="58e1b-143">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="58e1b-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="58e1b-144">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="58e1b-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="58e1b-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="58e1b-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="58e1b-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="58e1b-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="58e1b-147">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="58e1b-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="58e1b-148">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="58e1b-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="58e1b-149">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="58e1b-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="58e1b-150">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="58e1b-150">-   FindByExtension</span></span><br /><span data-ttu-id="58e1b-151">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="58e1b-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="58e1b-152">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="58e1b-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="58e1b-153">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="58e1b-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="58e1b-154">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="58e1b-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58e1b-155">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58e1b-155">Child Elements</span></span>  
 <span data-ttu-id="58e1b-156">Keine</span><span class="sxs-lookup"><span data-stu-id="58e1b-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58e1b-157">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58e1b-157">Parent Elements</span></span>  
  
|<span data-ttu-id="58e1b-158">Element</span><span class="sxs-lookup"><span data-stu-id="58e1b-158">Element</span></span>|<span data-ttu-id="58e1b-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58e1b-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58e1b-160">\<peer></span><span class="sxs-lookup"><span data-stu-id="58e1b-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="58e1b-161">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58e1b-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58e1b-162">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58e1b-162">Remarks</span></span>  
 <span data-ttu-id="58e1b-163">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="58e1b-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="58e1b-164">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="58e1b-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58e1b-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58e1b-165">Example</span></span>  
 <span data-ttu-id="58e1b-166">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="58e1b-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58e1b-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58e1b-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="58e1b-168">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="58e1b-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="58e1b-169">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="58e1b-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="58e1b-170">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="58e1b-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="58e1b-171">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="58e1b-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="58e1b-172">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="58e1b-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
