---
title: '&lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00567c32b800bb98386e15b2ba822ccc9623d72b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="7e89e-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="7e89e-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="7e89e-103">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="7e89e-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="7e89e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7e89e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7e89e-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="7e89e-105">\<behaviors></span></span>  
<span data-ttu-id="7e89e-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7e89e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7e89e-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="7e89e-107">\<behavior></span></span>  
<span data-ttu-id="7e89e-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="7e89e-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e89e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e89e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e89e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7e89e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e89e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e89e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e89e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7e89e-112">Attributes</span></span>  
  
|<span data-ttu-id="7e89e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7e89e-113">Attribute</span></span>|<span data-ttu-id="7e89e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e89e-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="7e89e-115">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="7e89e-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e89e-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e89e-116">Child Elements</span></span>  
  
|<span data-ttu-id="7e89e-117">Element</span><span class="sxs-lookup"><span data-stu-id="7e89e-117">Element</span></span>|<span data-ttu-id="7e89e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e89e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e89e-119">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="7e89e-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="7e89e-120">Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e89e-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="7e89e-121">Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="7e89e-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="7e89e-123">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="7e89e-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="7e89e-124">Gibt das aktuell ausgegebene Token für diesen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="7e89e-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="7e89e-126">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="7e89e-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="7e89e-127">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="7e89e-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="7e89e-129">\<SecureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="7e89e-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="7e89e-130">Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="7e89e-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="7e89e-132">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7e89e-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="7e89e-133">Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e89e-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="7e89e-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="7e89e-135">\<UserNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="7e89e-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="7e89e-136">Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="7e89e-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="7e89e-138">\<WindowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="7e89e-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="7e89e-139">Gibt die Einstellungen für die Validierung der Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="7e89e-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7e89e-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e89e-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e89e-141">Parent Elements</span></span>  
  
|<span data-ttu-id="7e89e-142">Element</span><span class="sxs-lookup"><span data-stu-id="7e89e-142">Element</span></span>|<span data-ttu-id="7e89e-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e89e-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e89e-144">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="7e89e-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7e89e-145">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="7e89e-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e89e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e89e-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="7e89e-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="7e89e-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
