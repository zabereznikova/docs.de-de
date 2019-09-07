---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399647"
---
# <a name="servicecredentials"></a><span data-ttu-id="0a4b5-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0a4b5-101">\<serviceCredentials></span></span>
<span data-ttu-id="0a4b5-102">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
<span data-ttu-id="0a4b5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a4b5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a4b5-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0a4b5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0a4b5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0a4b5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0a4b5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0a4b5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="0a4b5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0a4b5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="0a4b5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicecreden->**</span><span class="sxs-lookup"><span data-stu-id="0a4b5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4b5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a4b5-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a4b5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a4b5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0a4b5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a4b5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a4b5-112">Attributes</span></span>  
  
|<span data-ttu-id="0a4b5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0a4b5-113">Attribute</span></span>|<span data-ttu-id="0a4b5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a4b5-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0a4b5-115">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a4b5-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a4b5-116">Child Elements</span></span>  
  
|<span data-ttu-id="0a4b5-117">Element</span><span class="sxs-lookup"><span data-stu-id="0a4b5-117">Element</span></span>|<span data-ttu-id="0a4b5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a4b5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a4b5-119">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="0a4b5-119">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="0a4b5-120">Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="0a4b5-121">Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="0a4b5-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="0a4b5-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="0a4b5-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="0a4b5-124">Gibt das aktuell ausgegebene Token für diesen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="0a4b5-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="0a4b5-126">\<peer></span><span class="sxs-lookup"><span data-stu-id="0a4b5-126">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="0a4b5-127">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="0a4b5-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="0a4b5-129">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="0a4b5-129">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="0a4b5-130">Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="0a4b5-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="0a4b5-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="0a4b5-132">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="0a4b5-133">Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="0a4b5-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="0a4b5-135">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="0a4b5-135">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="0a4b5-136">Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="0a4b5-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="0a4b5-138">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="0a4b5-138">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="0a4b5-139">Gibt die Einstellungen für die Überprüfung der Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="0a4b5-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a4b5-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a4b5-141">Parent Elements</span></span>  
  
|<span data-ttu-id="0a4b5-142">Element</span><span class="sxs-lookup"><span data-stu-id="0a4b5-142">Element</span></span>|<span data-ttu-id="0a4b5-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a4b5-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a4b5-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0a4b5-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0a4b5-145">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="0a4b5-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a4b5-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a4b5-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="0a4b5-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="0a4b5-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
