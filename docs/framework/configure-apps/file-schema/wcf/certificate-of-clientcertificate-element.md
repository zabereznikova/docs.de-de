---
title: <certificate> of- <clientCertificate> Element
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 35ea3814e208921abaf44e6ef431c4e1b44cde60
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151140"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="9c296-102">\<certificate> of- \<clientCertificate> Element</span><span class="sxs-lookup"><span data-stu-id="9c296-102">\<certificate> of \<clientCertificate> Element</span></span>

<span data-ttu-id="9c296-103">Gibt ein X.509-Zertifikat an, das verwendet wird, um Nachrichten zu signieren und zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="9c296-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="9c296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c296-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c296-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c296-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9c296-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c296-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c296-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="9c296-107">Attributes</span></span>  
  
|<span data-ttu-id="9c296-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9c296-108">Attribute</span></span>|<span data-ttu-id="9c296-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c296-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="9c296-110">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c296-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9c296-111">Der im Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9c296-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="9c296-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c296-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="9c296-113">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Serverzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c296-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="9c296-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9c296-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9c296-115">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="9c296-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="9c296-116">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="9c296-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="9c296-117">Der Standardwert ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="9c296-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="9c296-118">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c296-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="9c296-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9c296-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9c296-120">-Addressbook: der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9c296-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="9c296-121">-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="9c296-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="9c296-122">-CertificationAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="9c296-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="9c296-123">-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="9c296-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="9c296-124">-My: Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="9c296-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="9c296-125">-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="9c296-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="9c296-126">-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="9c296-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="9c296-127">-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="9c296-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="9c296-128">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="9c296-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="9c296-129">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c296-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="9c296-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9c296-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9c296-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="9c296-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="9c296-132">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="9c296-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="9c296-133">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="9c296-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="9c296-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="9c296-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="9c296-135">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="9c296-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="9c296-136">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="9c296-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="9c296-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="9c296-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="9c296-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="9c296-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="9c296-139">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="9c296-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="9c296-140">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="9c296-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="9c296-141">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="9c296-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="9c296-142">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="9c296-142">-   FindByExtension</span></span><br /><span data-ttu-id="9c296-143">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="9c296-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="9c296-144">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="9c296-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="9c296-145">Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9c296-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="9c296-146">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="9c296-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c296-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c296-147">Child Elements</span></span>  

 <span data-ttu-id="9c296-148">Keine</span><span class="sxs-lookup"><span data-stu-id="9c296-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c296-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c296-149">Parent Elements</span></span>  
  
|<span data-ttu-id="9c296-150">Element</span><span class="sxs-lookup"><span data-stu-id="9c296-150">Element</span></span>|<span data-ttu-id="9c296-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c296-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="9c296-152">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9c296-152">Remarks</span></span>  

 <span data-ttu-id="9c296-153">Das `<certificate>`-Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="9c296-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="9c296-154">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="9c296-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="9c296-155">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c296-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="9c296-156">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="9c296-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="9c296-157">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="9c296-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="9c296-158">Weitere Informationen zu Duplex Diensten finden Sie unter Gewusst [wie: Erstellen eines Duplex Vertrags](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="9c296-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c296-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c296-159">Example</span></span>  

 <span data-ttu-id="9c296-160">Der folgende Code gibt an, wie Sie ein geeignetes X.509-Zertifikat und einen benutzerdefinierten Validierungstyp im `<authentication>`-Element suchen.</span><span class="sxs-lookup"><span data-stu-id="9c296-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
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
  
## <a name="see-also"></a><span data-ttu-id="9c296-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c296-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="9c296-162">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="9c296-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9c296-163">Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="9c296-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="9c296-164">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="9c296-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
