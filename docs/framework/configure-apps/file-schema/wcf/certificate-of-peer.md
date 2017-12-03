---
title: '&lt;certificate&gt; von &lt;peer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8bf8cb80201f2501fb60df7c9abb5039d688dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="65869-102">&lt;certificate&gt; von &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="65869-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="65869-103">Gibt ein von einem Peer verwendetes Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="65869-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="65869-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="65869-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="65869-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="65869-105">\<behaviors></span></span>  
<span data-ttu-id="65869-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="65869-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="65869-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="65869-107">\<behavior></span></span>  
<span data-ttu-id="65869-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="65869-108">\<serviceCredentials></span></span>  
<span data-ttu-id="65869-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="65869-109">\<peer></span></span>  
<span data-ttu-id="65869-110">\<Zertifikat ></span><span class="sxs-lookup"><span data-stu-id="65869-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65869-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="65869-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65869-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="65869-112">Attributes and Elements</span></span>  
 <span data-ttu-id="65869-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65869-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65869-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="65869-114">Attributes</span></span>  
  
|<span data-ttu-id="65869-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="65869-115">Attribute</span></span>|<span data-ttu-id="65869-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65869-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="65869-117">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="65869-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="65869-118">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="65869-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="65869-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="65869-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="65869-120">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="65869-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="65869-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="65869-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="65869-122">-LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="65869-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="65869-123">-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="65869-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="65869-124">Die Standardeinstellung ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="65869-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="65869-125">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65869-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="65869-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="65869-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="65869-127">-AddressBook: Zertifikatspeicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="65869-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="65869-128">-AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="65869-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="65869-129">-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="65869-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="65869-130">-Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="65869-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="65869-131">-My: Der Zertifikatspeicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="65869-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="65869-132">-Root: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstelle (CA).</span><span class="sxs-lookup"><span data-stu-id="65869-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="65869-133">-TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="65869-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="65869-134">-TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="65869-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="65869-135">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="65869-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="65869-136">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="65869-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="65869-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="65869-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="65869-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="65869-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="65869-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="65869-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="65869-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="65869-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="65869-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="65869-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="65869-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="65869-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="65869-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="65869-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="65869-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="65869-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="65869-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="65869-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="65869-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="65869-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="65869-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="65869-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="65869-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="65869-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="65869-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="65869-149">-   FindByExtension</span></span><br /><span data-ttu-id="65869-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="65869-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="65869-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="65869-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="65869-152">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="65869-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="65869-153">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="65869-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65869-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65869-154">Child Elements</span></span>  
 <span data-ttu-id="65869-155">Keine</span><span class="sxs-lookup"><span data-stu-id="65869-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65869-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65869-156">Parent Elements</span></span>  
  
|<span data-ttu-id="65869-157">Element</span><span class="sxs-lookup"><span data-stu-id="65869-157">Element</span></span>|<span data-ttu-id="65869-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65869-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65869-159">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="65869-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="65869-160">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="65869-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65869-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65869-161">Remarks</span></span>  
 <span data-ttu-id="65869-162">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete `X509Certificate2`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="65869-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="65869-163">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerken](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="65869-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65869-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65869-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="65869-165">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="65869-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="65869-166">Peer-zu-Peer-Netzwerken</span><span class="sxs-lookup"><span data-stu-id="65869-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="65869-167">Peerkanal Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="65869-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="65869-168">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="65869-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="65869-169">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="65869-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="65869-170">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="65869-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
