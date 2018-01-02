---
title: '&lt;clientCertificate&gt; von &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0bd36f0c13aebb75bb9d2147e871224c162b862
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="5bdbf-102">&lt;clientCertificate&gt; von &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="5bdbf-102">&lt;clientCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="5bdbf-103">Definiert ein X.509-Zertifikat, das zum Signieren und Verschlüsseln von Nachrichten an einen Client von einem Dienst in einem Duplexkommunikationsmuster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="5bdbf-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5bdbf-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-105">\<behaviors></span></span>  
<span data-ttu-id="5bdbf-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5bdbf-107">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="5bdbf-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-108">\<behavior></span></span>  
<span data-ttu-id="5bdbf-109">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-109">\<serviceCredentials></span></span>  
<span data-ttu-id="5bdbf-110">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bdbf-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bdbf-111">Syntax</span></span>  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bdbf-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5bdbf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5bdbf-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bdbf-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="5bdbf-114">Attributes</span></span>  
 <span data-ttu-id="5bdbf-115">Keine</span><span class="sxs-lookup"><span data-stu-id="5bdbf-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5bdbf-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5bdbf-116">Child Elements</span></span>  
  
|<span data-ttu-id="5bdbf-117">Element</span><span class="sxs-lookup"><span data-stu-id="5bdbf-117">Element</span></span>|<span data-ttu-id="5bdbf-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bdbf-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bdbf-119">\<Authentifizierung ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="5bdbf-120">Gibt Authentifizierungsoptionen für das Clientzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="5bdbf-121">\<Zertifikat ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="5bdbf-122">Gibt das zu verwendende Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bdbf-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5bdbf-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5bdbf-124">Element</span><span class="sxs-lookup"><span data-stu-id="5bdbf-124">Element</span></span>|<span data-ttu-id="5bdbf-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bdbf-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bdbf-126">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5bdbf-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="5bdbf-127">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bdbf-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bdbf-128">Remarks</span></span>  
 <span data-ttu-id="5bdbf-129">Dieses Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="5bdbf-130">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="5bdbf-131">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="5bdbf-132">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="5bdbf-133">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="5bdbf-134">Weitere Informationen über duplexdienste finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="5bdbf-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="5bdbf-135">Das in diesem Element festgelegte Zertifikat wird nur bei Bindungen, die mit dem `MutualCertificateDuplex`-Authentifizierungsmodus für die Nachrichtensicherheit konfiguriert sind, zum Verschlüsseln von Nachrichten für Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bdbf-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdbf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bdbf-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [<span data-ttu-id="5bdbf-137">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="5bdbf-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="5bdbf-138">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="5bdbf-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="5bdbf-139">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="5bdbf-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
