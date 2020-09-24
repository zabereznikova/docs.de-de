---
title: <certificate>-Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 8cc0404a5896dd23cffce6f1f77b91a2f01f23d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151089"
---
# <a name="certificate-element"></a><span data-ttu-id="f8904-102">\<certificate>-Element</span><span class="sxs-lookup"><span data-stu-id="f8904-102">\<certificate> Element</span></span>

<span data-ttu-id="f8904-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f8904-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="f8904-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8904-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8904-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f8904-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f8904-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8904-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8904-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="f8904-107">Attributes</span></span>  
  
|<span data-ttu-id="f8904-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f8904-108">Attribute</span></span>|<span data-ttu-id="f8904-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8904-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f8904-110">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8904-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f8904-111">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f8904-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="f8904-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f8904-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f8904-113">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8904-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="f8904-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="f8904-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f8904-115">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="f8904-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f8904-116">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="f8904-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f8904-117">Der Standardwert ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f8904-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f8904-118">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8904-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f8904-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="f8904-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f8904-120">-Addressbook: der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f8904-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f8904-121">-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="f8904-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f8904-122">-CertificateAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="f8904-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f8904-123">-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="f8904-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f8904-124">-My: Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="f8904-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f8904-125">-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="f8904-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f8904-126">-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f8904-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="f8904-127">-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="f8904-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="f8904-128">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="f8904-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="f8904-129">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8904-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f8904-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="f8904-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f8904-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="f8904-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="f8904-132">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="f8904-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="f8904-133">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="f8904-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f8904-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="f8904-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="f8904-135">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="f8904-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f8904-136">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="f8904-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f8904-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="f8904-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="f8904-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="f8904-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f8904-139">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="f8904-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="f8904-140">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="f8904-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f8904-141">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="f8904-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f8904-142">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="f8904-142">-   FindByExtension</span></span><br /><span data-ttu-id="f8904-143">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="f8904-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f8904-144">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="f8904-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f8904-145">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f8904-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="f8904-146">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="f8904-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8904-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8904-147">Child Elements</span></span>  

 <span data-ttu-id="f8904-148">Keine</span><span class="sxs-lookup"><span data-stu-id="f8904-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8904-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8904-149">Parent Elements</span></span>  
  
|<span data-ttu-id="f8904-150">Element</span><span class="sxs-lookup"><span data-stu-id="f8904-150">Element</span></span>|<span data-ttu-id="f8904-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8904-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="f8904-152">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8904-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8904-153">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f8904-153">Remarks</span></span>  

 <span data-ttu-id="f8904-154">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="f8904-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="f8904-155">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="f8904-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8904-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8904-156">Example</span></span>  

 <span data-ttu-id="f8904-157">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="f8904-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8904-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8904-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="f8904-159">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="f8904-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f8904-160">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="f8904-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="f8904-161">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f8904-161">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f8904-162">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f8904-162">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f8904-163">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="f8904-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
