---
title: <certificate> von <peer>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: 8ec839df02af4a01d31192eebc96e4c5e58313e9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151115"
---
# <a name="certificate-of-peer"></a><span data-ttu-id="06ce7-102">\<certificate> von \<peer></span><span class="sxs-lookup"><span data-stu-id="06ce7-102">\<certificate> of \<peer></span></span>

<span data-ttu-id="06ce7-103">Gibt ein von einem Peer verwendetes Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="06ce7-103">Specifies a certificate used by a peer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="06ce7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06ce7-104">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06ce7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="06ce7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="06ce7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06ce7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06ce7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="06ce7-107">Attributes</span></span>  
  
|<span data-ttu-id="06ce7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="06ce7-108">Attribute</span></span>|<span data-ttu-id="06ce7-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06ce7-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="06ce7-110">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="06ce7-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="06ce7-111">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="06ce7-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="06ce7-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="06ce7-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="06ce7-113">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="06ce7-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="06ce7-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="06ce7-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06ce7-115">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="06ce7-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="06ce7-116">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="06ce7-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="06ce7-117">Der Standardwert ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="06ce7-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="06ce7-118">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06ce7-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="06ce7-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="06ce7-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06ce7-120">-Addressbook: der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="06ce7-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="06ce7-121">-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="06ce7-121">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="06ce7-122">-CertificateAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="06ce7-122">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="06ce7-123">-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="06ce7-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="06ce7-124">-My: Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="06ce7-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="06ce7-125">-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen (CAS).</span><span class="sxs-lookup"><span data-stu-id="06ce7-125">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="06ce7-126">-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="06ce7-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="06ce7-127">-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="06ce7-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="06ce7-128">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="06ce7-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="06ce7-129">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="06ce7-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="06ce7-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="06ce7-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06ce7-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="06ce7-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="06ce7-132">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="06ce7-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="06ce7-133">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="06ce7-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="06ce7-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="06ce7-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="06ce7-135">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="06ce7-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="06ce7-136">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="06ce7-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="06ce7-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="06ce7-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="06ce7-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="06ce7-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="06ce7-139">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="06ce7-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="06ce7-140">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="06ce7-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="06ce7-141">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="06ce7-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="06ce7-142">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="06ce7-142">-   FindByExtension</span></span><br /><span data-ttu-id="06ce7-143">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="06ce7-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="06ce7-144">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="06ce7-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="06ce7-145">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="06ce7-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="06ce7-146">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="06ce7-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06ce7-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06ce7-147">Child Elements</span></span>  

 <span data-ttu-id="06ce7-148">Keine</span><span class="sxs-lookup"><span data-stu-id="06ce7-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06ce7-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06ce7-149">Parent Elements</span></span>  
  
|<span data-ttu-id="06ce7-150">Element</span><span class="sxs-lookup"><span data-stu-id="06ce7-150">Element</span></span>|<span data-ttu-id="06ce7-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06ce7-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="06ce7-152">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="06ce7-152">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06ce7-153">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="06ce7-153">Remarks</span></span>  

 <span data-ttu-id="06ce7-154">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete `X509Certificate2`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="06ce7-154">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="06ce7-155">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="06ce7-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ce7-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06ce7-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="06ce7-157">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="06ce7-157">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="06ce7-158">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="06ce7-158">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="06ce7-159">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="06ce7-159">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="06ce7-160">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="06ce7-160">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="06ce7-161">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="06ce7-161">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="06ce7-162">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="06ce7-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
