---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 54ac4f0aa31a4311976449d545880d825c06337d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256471"
---
# <a name="servicecredentials"></a><span data-ttu-id="731bf-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="731bf-101">\<serviceCredentials></span></span>
<span data-ttu-id="731bf-102">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="731bf-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="731bf-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="731bf-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="731bf-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="731bf-104">\<behaviors></span></span>  
<span data-ttu-id="731bf-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="731bf-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="731bf-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="731bf-106">\<behavior></span></span>  
<span data-ttu-id="731bf-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="731bf-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731bf-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="731bf-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="731bf-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="731bf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="731bf-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="731bf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="731bf-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="731bf-111">Attributes</span></span>  
  
|<span data-ttu-id="731bf-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="731bf-112">Attribute</span></span>|<span data-ttu-id="731bf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="731bf-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="731bf-114">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="731bf-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="731bf-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="731bf-115">Child Elements</span></span>  
  
|<span data-ttu-id="731bf-116">Element</span><span class="sxs-lookup"><span data-stu-id="731bf-116">Element</span></span>|<span data-ttu-id="731bf-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="731bf-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="731bf-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="731bf-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="731bf-119">Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="731bf-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="731bf-120">Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="731bf-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="731bf-121">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="731bf-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="731bf-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="731bf-123">Gibt das aktuell ausgegebene Token für diesen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="731bf-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="731bf-124">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="731bf-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="731bf-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="731bf-126">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="731bf-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="731bf-127">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="731bf-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="731bf-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="731bf-129">Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="731bf-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="731bf-130">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="731bf-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="731bf-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="731bf-132">Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="731bf-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="731bf-133">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="731bf-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="731bf-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="731bf-135">Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="731bf-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="731bf-136">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="731bf-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="731bf-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="731bf-138">Gibt die Einstellungen für die Validierung der Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="731bf-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="731bf-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="731bf-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="731bf-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="731bf-140">Parent Elements</span></span>  
  
|<span data-ttu-id="731bf-141">Element</span><span class="sxs-lookup"><span data-stu-id="731bf-141">Element</span></span>|<span data-ttu-id="731bf-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="731bf-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="731bf-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="731bf-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="731bf-144">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="731bf-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="731bf-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="731bf-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="731bf-146">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="731bf-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
