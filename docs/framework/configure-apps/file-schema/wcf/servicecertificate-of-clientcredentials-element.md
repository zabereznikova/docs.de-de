---
title: <serviceCertificate>of <clientCredentials> -Element
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: a3013d0f7efd3014892cf6400447d708809c5fcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936342"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="ed720-102">\<serviceCertificate-> \<von Clientanmelde Informationen >-Element</span><span class="sxs-lookup"><span data-stu-id="ed720-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="ed720-103">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ed720-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="ed720-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ed720-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ed720-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ed720-105">\<behaviors></span></span>  
<span data-ttu-id="ed720-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ed720-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ed720-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ed720-107">\<behavior></span></span>  
<span data-ttu-id="ed720-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ed720-108">\<clientCredentials></span></span>  
<span data-ttu-id="ed720-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="ed720-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed720-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed720-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed720-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed720-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ed720-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed720-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed720-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed720-113">Attributes</span></span>  
 <span data-ttu-id="ed720-114">Keine</span><span class="sxs-lookup"><span data-stu-id="ed720-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed720-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed720-115">Child Elements</span></span>  
  
|<span data-ttu-id="ed720-116">Element</span><span class="sxs-lookup"><span data-stu-id="ed720-116">Element</span></span>|<span data-ttu-id="ed720-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed720-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed720-118">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="ed720-118">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="ed720-119">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ed720-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="ed720-120">\<scopedzertifikate-></span><span class="sxs-lookup"><span data-stu-id="ed720-120">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="ed720-121">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ed720-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="ed720-122">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed720-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="ed720-123">\<authentication></span><span class="sxs-lookup"><span data-stu-id="ed720-123">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="ed720-124">Gibt die Authentifizierungsverhalten für Dienstzertifikate an, die von einem Client verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed720-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed720-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed720-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ed720-126">Element</span><span class="sxs-lookup"><span data-stu-id="ed720-126">Element</span></span>|<span data-ttu-id="ed720-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed720-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed720-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ed720-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="ed720-129">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ed720-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed720-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed720-130">Remarks</span></span>  
 <span data-ttu-id="ed720-131">Dieses Konfigurationselement gibt die Einstellungen an, anhand derer der Client das während der SSL-Authentifizierung vom Dienst bereitgestellte Zertifikat überprüft.</span><span class="sxs-lookup"><span data-stu-id="ed720-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="ed720-132">Enthält außerdem Zertifikate für den Dienst, die explizit auf dem Client für die Verschlüsselung von Nachrichten unter Verwendung der Nachrichtensicherheit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="ed720-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="ed720-133">Die Attribute des `serviceCertificate` -Elements sind identisch mit den Attributen [ \<des ClientCertificate->](clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="ed720-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed720-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed720-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="ed720-135">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="ed720-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ed720-136">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="ed720-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="ed720-137">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="ed720-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ed720-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ed720-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
