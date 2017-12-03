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
ms.openlocfilehash: d8e2fa4fe72b7b4c2f421aefa566f89492c06457
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="358eb-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="358eb-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="358eb-103">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="358eb-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="358eb-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="358eb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="358eb-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="358eb-105">\<behaviors></span></span>  
<span data-ttu-id="358eb-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="358eb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="358eb-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="358eb-107">\<behavior></span></span>  
<span data-ttu-id="358eb-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="358eb-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="358eb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="358eb-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="358eb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="358eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="358eb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="358eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="358eb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="358eb-112">Attributes</span></span>  
  
|<span data-ttu-id="358eb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="358eb-113">Attribute</span></span>|<span data-ttu-id="358eb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="358eb-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="358eb-115">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="358eb-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="358eb-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="358eb-116">Child Elements</span></span>  
  
|<span data-ttu-id="358eb-117">Element</span><span class="sxs-lookup"><span data-stu-id="358eb-117">Element</span></span>|<span data-ttu-id="358eb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="358eb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="358eb-119">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="358eb-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="358eb-120">Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="358eb-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="358eb-121">Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="358eb-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="358eb-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="358eb-123">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="358eb-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="358eb-124">Gibt das aktuell ausgegebene Token für diesen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="358eb-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="358eb-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="358eb-126">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="358eb-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="358eb-127">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="358eb-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="358eb-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="358eb-129">\<SecureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="358eb-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="358eb-130">Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="358eb-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="358eb-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="358eb-132">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="358eb-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="358eb-133">Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="358eb-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="358eb-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="358eb-135">\<UserNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="358eb-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="358eb-136">Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="358eb-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="358eb-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="358eb-138">\<WindowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="358eb-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="358eb-139">Gibt die Einstellungen für die Validierung der Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="358eb-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="358eb-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="358eb-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="358eb-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="358eb-141">Parent Elements</span></span>  
  
|<span data-ttu-id="358eb-142">Element</span><span class="sxs-lookup"><span data-stu-id="358eb-142">Element</span></span>|<span data-ttu-id="358eb-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="358eb-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="358eb-144">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="358eb-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="358eb-145">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="358eb-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="358eb-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="358eb-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="358eb-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="358eb-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
