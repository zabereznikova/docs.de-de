---
title: <serviceCertificate>of <clientCredentials> -Element
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399688"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="2c4c9-102">\<serviceCertificate-> \<von Clientanmelde Informationen >-Element</span><span class="sxs-lookup"><span data-stu-id="2c4c9-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="2c4c9-103">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="2c4c9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2c4c9-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2c4c9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2c4c9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="2c4c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="2c4c9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="2c4c9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="2c4c9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate->**</span><span class="sxs-lookup"><span data-stu-id="2c4c9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4c9-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c4c9-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c4c9-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2c4c9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2c4c9-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c4c9-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="2c4c9-114">Attributes</span></span>  
 <span data-ttu-id="2c4c9-115">Keine</span><span class="sxs-lookup"><span data-stu-id="2c4c9-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c4c9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c4c9-116">Child Elements</span></span>  
  
|<span data-ttu-id="2c4c9-117">Element</span><span class="sxs-lookup"><span data-stu-id="2c4c9-117">Element</span></span>|<span data-ttu-id="2c4c9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c4c9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c4c9-119">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="2c4c9-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="2c4c9-120">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="2c4c9-121">\<scopedzertifikate-></span><span class="sxs-lookup"><span data-stu-id="2c4c9-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="2c4c9-122">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="2c4c9-123">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="2c4c9-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="2c4c9-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="2c4c9-125">Gibt die Authentifizierungsverhalten für Dienstzertifikate an, die von einem Client verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c4c9-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c4c9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2c4c9-127">Element</span><span class="sxs-lookup"><span data-stu-id="2c4c9-127">Element</span></span>|<span data-ttu-id="2c4c9-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c4c9-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c4c9-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2c4c9-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="2c4c9-130">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c4c9-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c4c9-131">Remarks</span></span>  
 <span data-ttu-id="2c4c9-132">Dieses Konfigurationselement gibt die Einstellungen an, anhand derer der Client das während der SSL-Authentifizierung vom Dienst bereitgestellte Zertifikat überprüft.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="2c4c9-133">Enthält außerdem Zertifikate für den Dienst, die explizit auf dem Client für die Verschlüsselung von Nachrichten unter Verwendung der Nachrichtensicherheit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2c4c9-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="2c4c9-134">Die Attribute des `serviceCertificate` -Elements sind identisch mit den Attributen [ \<des ClientCertificate->](clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="2c4c9-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4c9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c4c9-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="2c4c9-136">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="2c4c9-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2c4c9-137">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="2c4c9-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2c4c9-138">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2c4c9-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2c4c9-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2c4c9-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
