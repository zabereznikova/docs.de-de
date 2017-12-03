---
title: '&lt;certificate&gt;-Element des &lt;clientCertificate&gt;-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aeb0479f661ed8f058f6c23ce79654ccb3a36fa0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a><span data-ttu-id="f4775-102">&lt;certificate&gt;-Element des &lt;clientCertificate&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="f4775-102">&lt;certificate&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="f4775-103">Gibt ein X.509-Zertifikat an, das verwendet wird, um Nachrichten zu signieren und zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="f4775-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="f4775-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f4775-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f4775-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f4775-105">\<behaviors></span></span>  
<span data-ttu-id="f4775-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f4775-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f4775-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f4775-107">\<behavior></span></span>  
<span data-ttu-id="f4775-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="f4775-108">\<serviceCredentials></span></span>  
<span data-ttu-id="f4775-109">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="f4775-109">\<clientCertificate></span></span>  
<span data-ttu-id="f4775-110">\<Zertifikat ></span><span class="sxs-lookup"><span data-stu-id="f4775-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4775-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4775-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4775-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f4775-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f4775-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4775-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4775-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4775-114">Attributes</span></span>  
  
|<span data-ttu-id="f4775-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="f4775-115">Attribute</span></span>|<span data-ttu-id="f4775-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4775-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f4775-117">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4775-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f4775-118">Der im Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f4775-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="f4775-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f4775-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f4775-120">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Serverzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4775-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="f4775-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f4775-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f4775-122">-LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="f4775-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f4775-123">-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="f4775-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f4775-124">Die Standardeinstellung ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f4775-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f4775-125">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4775-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f4775-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f4775-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f4775-127">-AddressBook: Zertifikatspeicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f4775-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f4775-128">-AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="f4775-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f4775-129">-CertificationAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen-Zertifikate (CAs).</span><span class="sxs-lookup"><span data-stu-id="f4775-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f4775-130">-Disallowed: Der Zertifikatspeicher für gesperrte Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="f4775-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f4775-131">-My: Der Zertifikatspeicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="f4775-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f4775-132">-Root: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="f4775-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f4775-133">-TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f4775-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="f4775-134">-TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="f4775-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="f4775-135">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="f4775-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="f4775-136">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4775-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f4775-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f4775-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f4775-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="f4775-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="f4775-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="f4775-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="f4775-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f4775-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f4775-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="f4775-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="f4775-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f4775-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f4775-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="f4775-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f4775-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="f4775-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="f4775-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="f4775-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f4775-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="f4775-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="f4775-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="f4775-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f4775-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="f4775-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f4775-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="f4775-149">-   FindByExtension</span></span><br /><span data-ttu-id="f4775-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="f4775-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f4775-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="f4775-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f4775-152">Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f4775-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="f4775-153">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="f4775-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4775-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4775-154">Child Elements</span></span>  
 <span data-ttu-id="f4775-155">Keine</span><span class="sxs-lookup"><span data-stu-id="f4775-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4775-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4775-156">Parent Elements</span></span>  
  
|<span data-ttu-id="f4775-157">Element</span><span class="sxs-lookup"><span data-stu-id="f4775-157">Element</span></span>|<span data-ttu-id="f4775-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4775-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4775-159">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="f4775-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="f4775-160">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4775-160">Remarks</span></span>  
 <span data-ttu-id="f4775-161">Das `<certificate>`-Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="f4775-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="f4775-162">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="f4775-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="f4775-163">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4775-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="f4775-164">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="f4775-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="f4775-165">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="f4775-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="f4775-166">Weitere Informationen über duplexdienste finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f4775-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4775-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4775-167">Example</span></span>  
 <span data-ttu-id="f4775-168">Der folgende Code gibt an, wie Sie ein geeignetes X.509-Zertifikat und einen benutzerdefinierten Validierungstyp im `<authentication>`-Element suchen.</span><span class="sxs-lookup"><span data-stu-id="f4775-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4775-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4775-169">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [<span data-ttu-id="f4775-170">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="f4775-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="f4775-171">Vorgehensweise: erstellen ein Diensts, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="f4775-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="f4775-172">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="f4775-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
