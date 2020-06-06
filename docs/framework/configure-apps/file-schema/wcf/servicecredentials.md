---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399647"
---
# \<serviceCredentials>
<span data-ttu-id="948e1-101">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="948e1-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="948e1-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="948e1-102">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="948e1-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="948e1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="948e1-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="948e1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="948e1-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="948e1-105">Attributes</span></span>  
  
|<span data-ttu-id="948e1-106">attribute</span><span class="sxs-lookup"><span data-stu-id="948e1-106">Attribute</span></span>|<span data-ttu-id="948e1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="948e1-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="948e1-108">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="948e1-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="948e1-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="948e1-109">Child Elements</span></span>  
  
|<span data-ttu-id="948e1-110">Element</span><span class="sxs-lookup"><span data-stu-id="948e1-110">Element</span></span>|<span data-ttu-id="948e1-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="948e1-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="948e1-112">Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="948e1-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="948e1-113">Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="948e1-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="948e1-114">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="948e1-115">Gibt das aktuell ausgegebene Token für diesen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="948e1-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="948e1-116">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="948e1-117">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="948e1-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="948e1-118">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="948e1-119">Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="948e1-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="948e1-120">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="948e1-121">Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="948e1-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="948e1-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="948e1-123">Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="948e1-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="948e1-124">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="948e1-125">Gibt die Einstellungen für die Überprüfung der Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="948e1-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="948e1-126">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="948e1-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="948e1-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="948e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="948e1-128">Element</span><span class="sxs-lookup"><span data-stu-id="948e1-128">Element</span></span>|<span data-ttu-id="948e1-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="948e1-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="948e1-130">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="948e1-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="948e1-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="948e1-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="948e1-132">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="948e1-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
