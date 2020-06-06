---
title: <serviceCertificate>of- <clientCredentials> Element
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399688"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="233e2-102">\<serviceCertificate>of- \<clientCredentials> Element</span><span class="sxs-lookup"><span data-stu-id="233e2-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="233e2-103">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="233e2-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="233e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="233e2-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="233e2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="233e2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="233e2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="233e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="233e2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="233e2-107">Attributes</span></span>  
 <span data-ttu-id="233e2-108">Keine</span><span class="sxs-lookup"><span data-stu-id="233e2-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="233e2-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="233e2-109">Child Elements</span></span>  
  
|<span data-ttu-id="233e2-110">Element</span><span class="sxs-lookup"><span data-stu-id="233e2-110">Element</span></span>|<span data-ttu-id="233e2-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="233e2-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="233e2-112">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="233e2-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="233e2-113">Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="233e2-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="233e2-114">Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.</span><span class="sxs-lookup"><span data-stu-id="233e2-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="233e2-115">Gibt die Authentifizierungsverhalten für Dienstzertifikate an, die von einem Client verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="233e2-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="233e2-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="233e2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="233e2-117">Element</span><span class="sxs-lookup"><span data-stu-id="233e2-117">Element</span></span>|<span data-ttu-id="233e2-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="233e2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="233e2-119">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="233e2-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="233e2-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="233e2-120">Remarks</span></span>  
 <span data-ttu-id="233e2-121">Dieses Konfigurationselement gibt die Einstellungen an, anhand derer der Client das während der SSL-Authentifizierung vom Dienst bereitgestellte Zertifikat überprüft.</span><span class="sxs-lookup"><span data-stu-id="233e2-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="233e2-122">Enthält außerdem Zertifikate für den Dienst, die explizit auf dem Client für die Verschlüsselung von Nachrichten unter Verwendung der Nachrichtensicherheit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="233e2-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="233e2-123">Die Attribute des- `serviceCertificate` Elements sind identisch mit den Attributen des-Elements [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="233e2-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233e2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="233e2-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="233e2-125">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="233e2-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="233e2-126">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="233e2-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="233e2-127">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="233e2-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="233e2-128">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="233e2-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
