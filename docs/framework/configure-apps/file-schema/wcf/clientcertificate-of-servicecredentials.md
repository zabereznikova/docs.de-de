---
title: <clientCertificate> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 9df49777efc80f425cad3b353f95db523a027214
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148916"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="0e162-102">\<clientCertificate> von \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0e162-102">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="0e162-103">Definiert ein X.509-Zertifikat, das zum Signieren und Verschlüsseln von Nachrichten an einen Client von einem Dienst in einem Duplexkommunikationsmuster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e162-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="0e162-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e162-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e162-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e162-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0e162-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e162-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e162-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e162-107">Attributes</span></span>  

 <span data-ttu-id="0e162-108">Keine</span><span class="sxs-lookup"><span data-stu-id="0e162-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e162-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e162-109">Child Elements</span></span>  
  
|<span data-ttu-id="0e162-110">Element</span><span class="sxs-lookup"><span data-stu-id="0e162-110">Element</span></span>|<span data-ttu-id="0e162-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e162-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="0e162-112">Gibt Authentifizierungsoptionen für das Clientzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="0e162-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="0e162-113">Gibt das zu verwendende Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="0e162-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e162-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e162-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0e162-115">Element</span><span class="sxs-lookup"><span data-stu-id="0e162-115">Element</span></span>|<span data-ttu-id="0e162-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e162-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="0e162-117">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="0e162-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e162-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0e162-118">Remarks</span></span>  

 <span data-ttu-id="0e162-119">Dieses Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="0e162-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="0e162-120">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="0e162-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="0e162-121">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e162-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="0e162-122">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="0e162-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="0e162-123">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="0e162-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="0e162-124">Weitere Informationen zu Duplex Diensten finden Sie unter Gewusst [wie: Erstellen eines Duplex Vertrags](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0e162-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="0e162-125">Das in diesem Element festgelegte Zertifikat wird nur bei Bindungen, die mit dem `MutualCertificateDuplex`-Authentifizierungsmodus für die Nachrichtensicherheit konfiguriert sind, zum Verschlüsseln von Nachrichten für Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e162-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e162-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e162-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="0e162-127">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="0e162-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="0e162-128">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="0e162-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0e162-129">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="0e162-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
