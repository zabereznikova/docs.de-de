---
title: <certificate>-Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400556"
---
# <a name="certificate-element"></a><span data-ttu-id="0c79d-102">\<certificate>-Element</span><span class="sxs-lookup"><span data-stu-id="0c79d-102">\<certificate> Element</span></span>
<span data-ttu-id="0c79d-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c79d-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="0c79d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c79d-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c79d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0c79d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0c79d-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c79d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c79d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0c79d-107">Attributes</span></span>  
  
|<span data-ttu-id="0c79d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="0c79d-108">Attribute</span></span>|<span data-ttu-id="0c79d-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c79d-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="0c79d-110">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c79d-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="0c79d-111">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0c79d-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="0c79d-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0c79d-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="0c79d-113">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c79d-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="0c79d-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c79d-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c79d-115">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="0c79d-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="0c79d-116">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="0c79d-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="0c79d-117">Der Standardwert ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0c79d-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="0c79d-118">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c79d-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="0c79d-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c79d-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c79d-120">-Addressbook: der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0c79d-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="0c79d-121">-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="0c79d-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="0c79d-122">-CertificateAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="0c79d-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="0c79d-123">-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="0c79d-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="0c79d-124">-My: Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="0c79d-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="0c79d-125">-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="0c79d-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="0c79d-126">-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0c79d-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="0c79d-127">-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="0c79d-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="0c79d-128">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="0c79d-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="0c79d-129">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c79d-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="0c79d-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c79d-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c79d-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="0c79d-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="0c79d-132">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="0c79d-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="0c79d-133">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="0c79d-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="0c79d-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="0c79d-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="0c79d-135">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="0c79d-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="0c79d-136">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="0c79d-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="0c79d-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="0c79d-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="0c79d-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="0c79d-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="0c79d-139">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="0c79d-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="0c79d-140">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="0c79d-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="0c79d-141">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="0c79d-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="0c79d-142">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="0c79d-142">-   FindByExtension</span></span><br /><span data-ttu-id="0c79d-143">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="0c79d-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="0c79d-144">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="0c79d-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="0c79d-145">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0c79d-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="0c79d-146">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="0c79d-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c79d-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c79d-147">Child Elements</span></span>  
 <span data-ttu-id="0c79d-148">Keine</span><span class="sxs-lookup"><span data-stu-id="0c79d-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c79d-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c79d-149">Parent Elements</span></span>  
  
|<span data-ttu-id="0c79d-150">Element</span><span class="sxs-lookup"><span data-stu-id="0c79d-150">Element</span></span>|<span data-ttu-id="0c79d-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c79d-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="0c79d-152">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c79d-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c79d-153">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0c79d-153">Remarks</span></span>  
 <span data-ttu-id="0c79d-154">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0c79d-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="0c79d-155">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="0c79d-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c79d-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c79d-156">Example</span></span>  
 <span data-ttu-id="0c79d-157">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="0c79d-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c79d-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c79d-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="0c79d-159">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="0c79d-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0c79d-160">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="0c79d-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="0c79d-161">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0c79d-161">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="0c79d-162">[Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0c79d-162">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="0c79d-163">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="0c79d-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
