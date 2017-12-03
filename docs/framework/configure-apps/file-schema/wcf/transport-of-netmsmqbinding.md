---
title: '&lt;transport&gt; von &lt;netMsmqBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 51dcdc268a012cb8298dbc380c9c5d33a9db8d02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="877d8-102">&lt;transport&gt; von &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="877d8-102">&lt;transport&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="877d8-103">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="877d8-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="877d8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="877d8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="877d8-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="877d8-105">\<bindings></span></span>  
<span data-ttu-id="877d8-106">\<NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="877d8-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="877d8-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="877d8-107">\<binding></span></span>  
<span data-ttu-id="877d8-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="877d8-108">\<security></span></span>  
<span data-ttu-id="877d8-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="877d8-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="877d8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="877d8-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="877d8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="877d8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="877d8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="877d8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="877d8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="877d8-113">Attributes</span></span>  
  
|<span data-ttu-id="877d8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="877d8-114">Attribute</span></span>|<span data-ttu-id="877d8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="877d8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="877d8-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="877d8-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="877d8-117">Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="877d8-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="877d8-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="877d8-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="877d8-119">-Keine: Keine Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="877d8-119">-   None: No authentication.</span></span><br /><span data-ttu-id="877d8-120">-WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory das x. 509-Zertifikat für die Sicherheits-ID der Nachricht zugeordnete abgerufen.</span><span class="sxs-lookup"><span data-stu-id="877d8-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="877d8-121">Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben für die Warteschlange verfügt.</span><span class="sxs-lookup"><span data-stu-id="877d8-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="877d8-122">-Certificate: Der Kanal Ruft das Zertifikat aus dem Zertifikatspeicher ab.</span><span class="sxs-lookup"><span data-stu-id="877d8-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="877d8-123">Die Standardeinstellung ist `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="877d8-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="877d8-124">Wenn dieses Attribut auf `None` festgelegt ist, muss das `msmqProtectionLevel`-Attribut auch auf `None` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="877d8-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="877d8-125">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="877d8-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="877d8-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="877d8-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="877d8-127">Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="877d8-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="877d8-128">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="877d8-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="877d8-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="877d8-129">-   RC4Stream</span></span><br /><span data-ttu-id="877d8-130">-AES</span><span class="sxs-lookup"><span data-stu-id="877d8-130">-   AES</span></span><br /><span data-ttu-id="877d8-131">– Der Standardwert ist `RC4Stream`.</span><span class="sxs-lookup"><span data-stu-id="877d8-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="877d8-132">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="877d8-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="877d8-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="877d8-133">msmqProtectionLevel</span></span>|<span data-ttu-id="877d8-134">Gibt an, wie die Nachrichten auf der Ebene des MSMQ-Transports gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="877d8-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="877d8-135">Durch die Verschlüsselung wird Nachrichtenintegrität bereitgestellt, während durch Signatur und Verschlüsselung sowohl die Nachrichtenintegrität als auch die Nachweisbarkeit sichergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="877d8-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="877d8-136">Das bedeutet, dass sichergestellt werden kann, dass die Nachricht tatsächlich vom Absender stammt und der Absender die Person ist, die er vorgibt zu sein.</span><span class="sxs-lookup"><span data-stu-id="877d8-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="877d8-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="877d8-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="877d8-138">-None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="877d8-138">-   None: No protection.</span></span><br /><span data-ttu-id="877d8-139">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="877d8-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="877d8-140">-EncryptAndSign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="877d8-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="877d8-141">– Der Standardwert ist `Sign`.</span><span class="sxs-lookup"><span data-stu-id="877d8-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="877d8-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="877d8-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="877d8-143">Gibt den Hashalgorithmus für die Berechnung des Nachrichtenhashs.</span><span class="sxs-lookup"><span data-stu-id="877d8-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="877d8-144">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="877d8-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="877d8-145">-MD5</span><span class="sxs-lookup"><span data-stu-id="877d8-145">-   MD5</span></span><br /><span data-ttu-id="877d8-146">-SHA1</span><span class="sxs-lookup"><span data-stu-id="877d8-146">-   SHA1</span></span><br /><span data-ttu-id="877d8-147">-SHA256</span><span class="sxs-lookup"><span data-stu-id="877d8-147">-   SHA256</span></span><br /><span data-ttu-id="877d8-148">-"SHA512" VERWENDET</span><span class="sxs-lookup"><span data-stu-id="877d8-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="877d8-149">Die Standardeinstellung ist `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="877d8-149">The default is `SHA1`.</span></span> <span data-ttu-id="877d8-150">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="877d8-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="877d8-151">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="877d8-151">Child Elements</span></span>  
 <span data-ttu-id="877d8-152">Keine</span><span class="sxs-lookup"><span data-stu-id="877d8-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="877d8-153">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="877d8-153">Parent Elements</span></span>  
  
|<span data-ttu-id="877d8-154">Element</span><span class="sxs-lookup"><span data-stu-id="877d8-154">Element</span></span>|<span data-ttu-id="877d8-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="877d8-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="877d8-156">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="877d8-156">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="877d8-157">Definiert die Transportsicherheitseinstellungen für in die Warteschlange gestellte Transporte.</span><span class="sxs-lookup"><span data-stu-id="877d8-157">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="877d8-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="877d8-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="877d8-159">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="877d8-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="877d8-160">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="877d8-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="877d8-161">Bindungen</span><span class="sxs-lookup"><span data-stu-id="877d8-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="877d8-162">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="877d8-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="877d8-163">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="877d8-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="877d8-164">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="877d8-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
