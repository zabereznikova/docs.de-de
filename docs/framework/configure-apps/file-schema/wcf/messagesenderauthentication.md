---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 496542ca476d9af309a34b4b05a1c3c023c06124
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="dd5d0-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5d0-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="dd5d0-103">Gibt Authentifizierungseinstellungen für ein Peerzertifikat an, das von einem Nachrichtenabsender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="dd5d0-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd5d0-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-105">\<behaviors></span></span>  
<span data-ttu-id="dd5d0-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dd5d0-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-107">\<behavior></span></span>  
<span data-ttu-id="dd5d0-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-108">\<serviceCredentials></span></span>  
<span data-ttu-id="dd5d0-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-109">\<peer></span></span>  
<span data-ttu-id="dd5d0-110">\<MessageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd5d0-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd5d0-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd5d0-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dd5d0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dd5d0-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd5d0-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="dd5d0-114">Attributes</span></span>  
  
|<span data-ttu-id="dd5d0-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="dd5d0-115">Attribute</span></span>|<span data-ttu-id="dd5d0-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd5d0-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="dd5d0-117">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-117">Optional enumeration.</span></span> <span data-ttu-id="dd5d0-118">Gibt einen von fünf die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="dd5d0-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="dd5d0-120">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="dd5d0-121">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-121">Optional string.</span></span> <span data-ttu-id="dd5d0-122">Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="dd5d0-123">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="dd5d0-124">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="dd5d0-125"> stellt ein standardmäßiges Peerzertifikats-Validierungssteuerelement bereit, das das Peerzertifikat gegen den Speicher vertrauenswürdiger Personen überprüft.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="dd5d0-126">Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="dd5d0-127">Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="dd5d0-128">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-128">Optional enumeration.</span></span> <span data-ttu-id="dd5d0-129">Legt den Zertifikatssperrmodus fest.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="dd5d0-130">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="dd5d0-131">Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="dd5d0-132">Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="dd5d0-133">Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="dd5d0-134">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-134">Optional enumeration.</span></span> <span data-ttu-id="dd5d0-135">Gibt den Ort des vertrauenswürdigen Speichers an, an dem das Peerzertifikat vom [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Sicherheitssystem überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="dd5d0-136">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd5d0-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dd5d0-137">Child Elements</span></span>  
 <span data-ttu-id="dd5d0-138">Keine</span><span class="sxs-lookup"><span data-stu-id="dd5d0-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd5d0-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dd5d0-139">Parent Elements</span></span>  
  
|<span data-ttu-id="dd5d0-140">Element</span><span class="sxs-lookup"><span data-stu-id="dd5d0-140">Element</span></span>|<span data-ttu-id="dd5d0-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd5d0-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd5d0-142">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="dd5d0-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="dd5d0-143">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd5d0-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd5d0-144">Remarks</span></span>  
 <span data-ttu-id="dd5d0-145">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="dd5d0-146">Für Ausgabekanäle, wird jede Nachricht signiert, mithilfe des bereitgestellten Zertifikats [ \<Zertifikat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="dd5d0-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="dd5d0-147">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="dd5d0-148">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="dd5d0-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd5d0-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd5d0-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="dd5d0-150">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="dd5d0-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="dd5d0-151">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="dd5d0-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="dd5d0-152">Peerkanal Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="dd5d0-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="dd5d0-153">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="dd5d0-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="dd5d0-154">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="dd5d0-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
