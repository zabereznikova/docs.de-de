---
title: '&lt;ServiceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b9e32509a5e182301455eaf0e602a03c51fbc23a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150772"
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="d1f47-102">&lt;ServiceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="d1f47-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="d1f47-103">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="d1f47-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="d1f47-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d1f47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1f47-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d1f47-105">\<behaviors></span></span>  
<span data-ttu-id="d1f47-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d1f47-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d1f47-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="d1f47-107">\<behavior></span></span>  
<span data-ttu-id="d1f47-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="d1f47-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f47-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1f47-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1f47-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d1f47-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d1f47-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d1f47-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1f47-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d1f47-112">Attributes</span></span>  
  
|<span data-ttu-id="d1f47-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="d1f47-113">Attribute</span></span>|<span data-ttu-id="d1f47-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1f47-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d1f47-115">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="d1f47-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1f47-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1f47-116">Child Elements</span></span>  
  
|<span data-ttu-id="d1f47-117">Element</span><span class="sxs-lookup"><span data-stu-id="d1f47-117">Element</span></span>|<span data-ttu-id="d1f47-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1f47-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1f47-119">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="d1f47-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="d1f47-120">Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d1f47-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="d1f47-121">Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="d1f47-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="d1f47-123">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d1f47-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="d1f47-124">Gibt das aktuell ausgegebene Token für diesen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="d1f47-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="d1f47-126">\<peer></span><span class="sxs-lookup"><span data-stu-id="d1f47-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="d1f47-127">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="d1f47-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="d1f47-129">\<SecureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d1f47-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="d1f47-130">Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="d1f47-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="d1f47-132">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d1f47-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="d1f47-133">Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1f47-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="d1f47-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="d1f47-135">\<UserNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d1f47-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="d1f47-136">Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="d1f47-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="d1f47-138">\<WindowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d1f47-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="d1f47-139">Gibt die Einstellungen für die Validierung der Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="d1f47-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="d1f47-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1f47-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1f47-141">Parent Elements</span></span>  
  
|<span data-ttu-id="d1f47-142">Element</span><span class="sxs-lookup"><span data-stu-id="d1f47-142">Element</span></span>|<span data-ttu-id="d1f47-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1f47-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1f47-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d1f47-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d1f47-145">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="d1f47-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1f47-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1f47-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="d1f47-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="d1f47-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
