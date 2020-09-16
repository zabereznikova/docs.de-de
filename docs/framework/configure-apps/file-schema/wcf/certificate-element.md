---
title: <certificate>-Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: c5fd156904ed30035991a8391c8f975da2a97ea7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554370"
---
# <a name="certificate-element"></a><span data-ttu-id="5e117-102">\<certificate>-Element</span><span class="sxs-lookup"><span data-stu-id="5e117-102">\<certificate> Element</span></span>
<span data-ttu-id="5e117-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e117-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="5e117-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e117-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e117-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e117-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5e117-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e117-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e117-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5e117-107">Attributes</span></span>  
  
|<span data-ttu-id="5e117-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5e117-108">Attribute</span></span>|<span data-ttu-id="5e117-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e117-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="5e117-110">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e117-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="5e117-111">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5e117-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="5e117-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5e117-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="5e117-113">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e117-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="5e117-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5e117-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e117-115">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="5e117-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="5e117-116">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="5e117-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="5e117-117">Der Standardwert ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="5e117-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="5e117-118">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e117-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="5e117-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5e117-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e117-120">-Addressbook: der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5e117-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="5e117-121">-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="5e117-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="5e117-122">-CertificateAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="5e117-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="5e117-123">-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="5e117-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="5e117-124">-My: Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="5e117-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="5e117-125">-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="5e117-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="5e117-126">-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="5e117-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="5e117-127">-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="5e117-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="5e117-128">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="5e117-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="5e117-129">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e117-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="5e117-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5e117-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e117-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="5e117-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="5e117-132">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="5e117-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="5e117-133">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="5e117-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="5e117-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="5e117-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="5e117-135">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="5e117-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="5e117-136">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="5e117-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="5e117-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="5e117-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="5e117-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="5e117-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="5e117-139">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="5e117-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="5e117-140">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="5e117-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="5e117-141">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="5e117-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="5e117-142">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="5e117-142">-   FindByExtension</span></span><br /><span data-ttu-id="5e117-143">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="5e117-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="5e117-144">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="5e117-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="5e117-145">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5e117-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="5e117-146">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="5e117-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e117-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e117-147">Child Elements</span></span>  
 <span data-ttu-id="5e117-148">Keine</span><span class="sxs-lookup"><span data-stu-id="5e117-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e117-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e117-149">Parent Elements</span></span>  
  
|<span data-ttu-id="5e117-150">Element</span><span class="sxs-lookup"><span data-stu-id="5e117-150">Element</span></span>|<span data-ttu-id="5e117-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e117-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="5e117-152">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e117-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e117-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e117-153">Remarks</span></span>  
 <span data-ttu-id="5e117-154">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5e117-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="5e117-155">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="5e117-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e117-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e117-156">Example</span></span>  
 <span data-ttu-id="5e117-157">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="5e117-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5e117-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e117-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="5e117-159">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="5e117-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5e117-160">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="5e117-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="5e117-161">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5e117-161">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="5e117-162">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5e117-162">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="5e117-163">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="5e117-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
