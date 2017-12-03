---
title: '&lt;transport&gt; von &lt;msmqIntegrationBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27b2ade7c9033ca82d3249ef18f1004e30c30025
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="1356a-102">&lt;transport&gt; von &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1356a-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="1356a-103">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="1356a-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="1356a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1356a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1356a-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="1356a-105">\<bindings></span></span>  
<span data-ttu-id="1356a-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="1356a-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="1356a-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="1356a-107">\<binding></span></span>  
<span data-ttu-id="1356a-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="1356a-108">\<security></span></span>  
<span data-ttu-id="1356a-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="1356a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1356a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1356a-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1356a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1356a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1356a-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1356a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1356a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1356a-113">Attributes</span></span>  
  
|<span data-ttu-id="1356a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="1356a-114">Attribute</span></span>|<span data-ttu-id="1356a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1356a-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="1356a-116">Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="1356a-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="1356a-117">Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="1356a-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="1356a-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="1356a-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1356a-119">-Keine: Keine Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1356a-119">-   None: No authentication.</span></span><br /><span data-ttu-id="1356a-120">-WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory, um das x. 509-Zertifikat abzurufen, für die mit der Nachricht SID verknüpfte.</span><span class="sxs-lookup"><span data-stu-id="1356a-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="1356a-121">Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.</span><span class="sxs-lookup"><span data-stu-id="1356a-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="1356a-122">-Certificate: Der Kanal Ruft das Zertifikat aus dem Zertifikatspeicher ab.</span><span class="sxs-lookup"><span data-stu-id="1356a-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="1356a-123">Der Standardwert ist WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="1356a-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="1356a-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="1356a-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="1356a-125">Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1356a-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="1356a-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="1356a-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1356a-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="1356a-127">-   RC4Stream</span></span><br /><span data-ttu-id="1356a-128">-AES</span><span class="sxs-lookup"><span data-stu-id="1356a-128">-   AES</span></span><br /><br /> <span data-ttu-id="1356a-129">Der Standardwert ist RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="1356a-129">The default value is RC4Stream.</span></span> <span data-ttu-id="1356a-130">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="1356a-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="1356a-131">Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="1356a-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="1356a-132">Mit der Verschlüsselung wird die Nachrichtenintegrität sichergestellt, während EncryptAndSign sowohl Nachrichtenintegrität als auch Nachweisbarkeit sicherstellt. Dabei wird geprüft, ob die Nachricht wirklich vom Absender kommt und der Absender wirklich der ist, der er vorgibt zu sein.</span><span class="sxs-lookup"><span data-stu-id="1356a-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="1356a-133">-Die folgenden: Gültige Werte</span><span class="sxs-lookup"><span data-stu-id="1356a-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="1356a-134">-None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="1356a-134">-   None: No protection.</span></span><br /><span data-ttu-id="1356a-135">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="1356a-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1356a-136">-EncryptAndSign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="1356a-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1356a-137">Der Standardwert ist Sign.</span><span class="sxs-lookup"><span data-stu-id="1356a-137">The default value is Sign.</span></span> <span data-ttu-id="1356a-138">Dieses Attribut ist vom Typ ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="1356a-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="1356a-139">-Gibt den Algorithmus zum Berechnen des Digests als Teil von Signaturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1356a-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="1356a-140">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="1356a-140">Valid values include the following:</span></span><br /><span data-ttu-id="1356a-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="1356a-141">-   MD5</span></span><br /><span data-ttu-id="1356a-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="1356a-142">-   SHA1</span></span><br /><span data-ttu-id="1356a-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="1356a-143">-   SHA256</span></span><br /><span data-ttu-id="1356a-144">-"SHA512" VERWENDET</span><span class="sxs-lookup"><span data-stu-id="1356a-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="1356a-145">Der Standardwert ist SHA1.</span><span class="sxs-lookup"><span data-stu-id="1356a-145">The default value is SHA1.</span></span> <span data-ttu-id="1356a-146">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="1356a-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1356a-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1356a-147">Child Elements</span></span>  
 <span data-ttu-id="1356a-148">Keine</span><span class="sxs-lookup"><span data-stu-id="1356a-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1356a-149">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1356a-149">Parent Elements</span></span>  
  
|<span data-ttu-id="1356a-150">Element</span><span class="sxs-lookup"><span data-stu-id="1356a-150">Element</span></span>|<span data-ttu-id="1356a-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1356a-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1356a-152">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="1356a-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="1356a-153">Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.</span><span class="sxs-lookup"><span data-stu-id="1356a-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1356a-154">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1356a-154">Remarks</span></span>  
 <span data-ttu-id="1356a-155">Dieses Element kapselt die Sicherheitseinstellungen für den Message Queuing-Integrationstransport ein.</span><span class="sxs-lookup"><span data-stu-id="1356a-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="1356a-156">Die Einstellungen für die Message Queuing-Integration und Transporte in der Warteschlange sind die gleichen.</span><span class="sxs-lookup"><span data-stu-id="1356a-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="1356a-157">Es ermöglicht das Festlegen des Authentifizierungsmodus, des Verschlüsselungsalgorithmus, des Secure Hash-Algorithmus sowie der Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="1356a-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1356a-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1356a-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="1356a-159">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1356a-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1356a-160">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1356a-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1356a-161">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1356a-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1356a-162">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="1356a-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1356a-163">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1356a-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1356a-164">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="1356a-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
