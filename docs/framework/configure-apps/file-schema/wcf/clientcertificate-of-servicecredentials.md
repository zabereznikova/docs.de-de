---
title: <clientCertificate> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 277e5e33bcc7f9d417da7ce24caa4c6200c23e23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919539"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="b66b7-102">\<ClientCertificate-> \<von servicecreden-></span><span class="sxs-lookup"><span data-stu-id="b66b7-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="b66b7-103">Definiert ein X.509-Zertifikat, das zum Signieren und Verschlüsseln von Nachrichten an einen Client von einem Dienst in einem Duplexkommunikationsmuster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b66b7-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="b66b7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b66b7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b66b7-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b66b7-105">\<behaviors></span></span>  
<span data-ttu-id="b66b7-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b66b7-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b66b7-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b66b7-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="b66b7-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b66b7-108">\<behavior></span></span>  
<span data-ttu-id="b66b7-109">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b66b7-109">\<serviceCredentials></span></span>  
<span data-ttu-id="b66b7-110">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="b66b7-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b66b7-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b66b7-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b66b7-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b66b7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b66b7-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b66b7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b66b7-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b66b7-114">Attributes</span></span>  
 <span data-ttu-id="b66b7-115">Keine</span><span class="sxs-lookup"><span data-stu-id="b66b7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b66b7-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b66b7-116">Child Elements</span></span>  
  
|<span data-ttu-id="b66b7-117">Element</span><span class="sxs-lookup"><span data-stu-id="b66b7-117">Element</span></span>|<span data-ttu-id="b66b7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b66b7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b66b7-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="b66b7-119">\<authentication></span></span>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="b66b7-120">Gibt Authentifizierungsoptionen für das Clientzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="b66b7-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="b66b7-121">\<certificate></span><span class="sxs-lookup"><span data-stu-id="b66b7-121">\<certificate></span></span>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="b66b7-122">Gibt das zu verwendende Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="b66b7-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b66b7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b66b7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b66b7-124">Element</span><span class="sxs-lookup"><span data-stu-id="b66b7-124">Element</span></span>|<span data-ttu-id="b66b7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b66b7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b66b7-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b66b7-126">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="b66b7-127">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="b66b7-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b66b7-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b66b7-128">Remarks</span></span>  
 <span data-ttu-id="b66b7-129">Dieses Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="b66b7-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="b66b7-130">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="b66b7-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="b66b7-131">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b66b7-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="b66b7-132">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b66b7-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="b66b7-133">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="b66b7-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="b66b7-134">Weitere Informationen zu Duplex Diensten finden [Sie unter Gewusst wie: Erstellen Sie einen Duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)Vertrag.</span><span class="sxs-lookup"><span data-stu-id="b66b7-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="b66b7-135">Das in diesem Element festgelegte Zertifikat wird nur bei Bindungen, die mit dem `MutualCertificateDuplex`-Authentifizierungsmodus für die Nachrichtensicherheit konfiguriert sind, zum Verschlüsseln von Nachrichten für Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="b66b7-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b66b7-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b66b7-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="b66b7-137">Vorgehensweise: Erstellen eines Duplex Vertrags</span><span class="sxs-lookup"><span data-stu-id="b66b7-137">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="b66b7-138">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="b66b7-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b66b7-139">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="b66b7-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
