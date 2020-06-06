---
title: <certificate>of- <clientCertificate> Element
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400546"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="a1f4b-102">\<certificate>of- \<clientCertificate> Element</span><span class="sxs-lookup"><span data-stu-id="a1f4b-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="a1f4b-103">Gibt ein X.509-Zertifikat an, das verwendet wird, um Nachrichten zu signieren und zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="a1f4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1f4b-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1f4b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1f4b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a1f4b-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1f4b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1f4b-107">Attributes</span></span>  
  
|<span data-ttu-id="a1f4b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a1f4b-108">Attribute</span></span>|<span data-ttu-id="a1f4b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a1f4b-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a1f4b-110">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a1f4b-111">Der im Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="a1f4b-112">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a1f4b-113">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Serverzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="a1f4b-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a1f4b-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1f4b-115">-LocalMachine: der dem lokalen Computer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a1f4b-116">-CurrentUser: der dem aktuellen Benutzer zugewiesene Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a1f4b-117">Der Standardwert ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="a1f4b-118">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="a1f4b-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a1f4b-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1f4b-120">-Addressbook: der Zertifikat Speicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a1f4b-121">-AuthRoot: der Zertifikat Speicher für Zertifizierungsstellen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="a1f4b-122">-CertificationAuthority: der Zertifikat Speicher für zwischen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="a1f4b-123">-Nicht zulässig: Zertifikat Speicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a1f4b-124">-My: Zertifikat Speicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a1f4b-125">-Root: der Zertifikat Speicher für vertrauenswürdige Stamm Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="a1f4b-126">-Treudpeople: der Zertifikat Speicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="a1f4b-127">-Treudpublisher: der Zertifikat Speicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="a1f4b-128">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="a1f4b-129">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a1f4b-130">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a1f4b-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1f4b-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="a1f4b-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a1f4b-132">-Findbysubjetname</span><span class="sxs-lookup"><span data-stu-id="a1f4b-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="a1f4b-133">-Findbysubjeterkennbare shedname</span><span class="sxs-lookup"><span data-stu-id="a1f4b-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a1f4b-134">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a1f4b-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="a1f4b-135">-Findbyissuerissushedname</span><span class="sxs-lookup"><span data-stu-id="a1f4b-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a1f4b-136">-Findbyserialnumber</span><span class="sxs-lookup"><span data-stu-id="a1f4b-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a1f4b-137">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a1f4b-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="a1f4b-138">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a1f4b-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a1f4b-139">-Findbytemplatename</span><span class="sxs-lookup"><span data-stu-id="a1f4b-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="a1f4b-140">-Findbyapplicationpolicy</span><span class="sxs-lookup"><span data-stu-id="a1f4b-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a1f4b-141">-Findbycertificatepolicy</span><span class="sxs-lookup"><span data-stu-id="a1f4b-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a1f4b-142">-Findbyextension</span><span class="sxs-lookup"><span data-stu-id="a1f4b-142">-   FindByExtension</span></span><br /><span data-ttu-id="a1f4b-143">-Findbykeyusage</span><span class="sxs-lookup"><span data-stu-id="a1f4b-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a1f4b-144">-Findbysubjetkeyidentifier</span><span class="sxs-lookup"><span data-stu-id="a1f4b-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a1f4b-145">Der im `findValue`-Attribut enthaltene Typ muss die Anforderungen in X509FindType erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="a1f4b-146">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1f4b-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1f4b-147">Child Elements</span></span>  
 <span data-ttu-id="a1f4b-148">Keine</span><span class="sxs-lookup"><span data-stu-id="a1f4b-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1f4b-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1f4b-149">Parent Elements</span></span>  
  
|<span data-ttu-id="a1f4b-150">Element</span><span class="sxs-lookup"><span data-stu-id="a1f4b-150">Element</span></span>|<span data-ttu-id="a1f4b-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a1f4b-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="a1f4b-152">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a1f4b-152">Remarks</span></span>  
 <span data-ttu-id="a1f4b-153">Das `<certificate>`-Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="a1f4b-154">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="a1f4b-155">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="a1f4b-156">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="a1f4b-157">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="a1f4b-158">Weitere Informationen zu Duplex Diensten finden Sie unter Gewusst [wie: Erstellen eines Duplex Vertrags](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a1f4b-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1f4b-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1f4b-159">Example</span></span>  
 <span data-ttu-id="a1f4b-160">Der folgende Code gibt an, wie Sie ein geeignetes X.509-Zertifikat und einen benutzerdefinierten Validierungstyp im `<authentication>`-Element suchen.</span><span class="sxs-lookup"><span data-stu-id="a1f4b-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1f4b-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1f4b-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="a1f4b-162">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="a1f4b-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a1f4b-163">Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="a1f4b-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="a1f4b-164">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="a1f4b-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
