---
title: <transport> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152930"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="35099-102">\<transport> von \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="35099-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="35099-103">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="35099-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="35099-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35099-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35099-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="35099-105">Attributes and Elements</span></span>  
 <span data-ttu-id="35099-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35099-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35099-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="35099-107">Attributes</span></span>  
  
|<span data-ttu-id="35099-108">attribute</span><span class="sxs-lookup"><span data-stu-id="35099-108">Attribute</span></span>|<span data-ttu-id="35099-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="35099-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35099-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="35099-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="35099-111">Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="35099-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="35099-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35099-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="35099-113">-None: keine Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35099-113">-   None: No authentication.</span></span><br /><span data-ttu-id="35099-114">-Windows Domain: der Authentifizierungsmechanismus verwendet Active Directory, um das X. 509-Zertifikat für die der Nachricht zugeordnete Sicherheits-ID abzurufen.</span><span class="sxs-lookup"><span data-stu-id="35099-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="35099-115">Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben für die Warteschlange verfügt.</span><span class="sxs-lookup"><span data-stu-id="35099-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="35099-116">-Certificate: der Kanal Ruft das Zertifikat aus dem Zertifikat Speicher ab.</span><span class="sxs-lookup"><span data-stu-id="35099-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="35099-117">Der Standardwert lautet `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="35099-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="35099-118">Wenn dieses Attribut auf `None` festgelegt ist, muss das `msmqProtectionLevel`-Attribut auch auf `None` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="35099-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="35099-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="35099-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="35099-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="35099-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="35099-121">Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35099-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="35099-122">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35099-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="35099-123">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="35099-123">-   RC4Stream</span></span><br /><span data-ttu-id="35099-124">-AES</span><span class="sxs-lookup"><span data-stu-id="35099-124">-   AES</span></span><br /><span data-ttu-id="35099-125">-Der Standardwert ist `RC4Stream` .</span><span class="sxs-lookup"><span data-stu-id="35099-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="35099-126">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="35099-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="35099-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="35099-127">msmqProtectionLevel</span></span>|<span data-ttu-id="35099-128">Gibt an, wie die Nachrichten auf der Ebene des MSMQ-Transports gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="35099-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="35099-129">Durch die Verschlüsselung wird Nachrichtenintegrität bereitgestellt, während durch Signatur und Verschlüsselung sowohl die Nachrichtenintegrität als auch die Nachweisbarkeit sichergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="35099-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="35099-130">Das heißt, die Nachricht stammt tatsächlich vom Absender, und der Absender ist die Person, die Sie sagen.</span><span class="sxs-lookup"><span data-stu-id="35099-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="35099-131">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35099-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="35099-132">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="35099-132">-   None: No protection.</span></span><br /><span data-ttu-id="35099-133">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="35099-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="35099-134">-Verschlüsseltandsign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="35099-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="35099-135">-Der Standardwert ist `Sign` .</span><span class="sxs-lookup"><span data-stu-id="35099-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="35099-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="35099-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="35099-137">Gibt den Hashalgorithmus für die Berechnung des Nachrichtenhashs an.</span><span class="sxs-lookup"><span data-stu-id="35099-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="35099-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35099-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="35099-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="35099-139">-   MD5</span></span><br /><span data-ttu-id="35099-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="35099-140">-   SHA1</span></span><br /><span data-ttu-id="35099-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="35099-141">-   SHA256</span></span><br /><span data-ttu-id="35099-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="35099-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="35099-143">Der Standardwert lautet `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="35099-143">The default is `SHA1`.</span></span> <span data-ttu-id="35099-144">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="35099-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="35099-145">Aufgrund von Konnektivitätsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="35099-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35099-146">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35099-146">Child Elements</span></span>  
 <span data-ttu-id="35099-147">Keine</span><span class="sxs-lookup"><span data-stu-id="35099-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35099-148">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35099-148">Parent Elements</span></span>  
  
|<span data-ttu-id="35099-149">Element</span><span class="sxs-lookup"><span data-stu-id="35099-149">Element</span></span>|<span data-ttu-id="35099-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35099-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="35099-151">Definiert die Transportsicherheitseinstellungen für in die Warteschlange gestellte Transporte.</span><span class="sxs-lookup"><span data-stu-id="35099-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35099-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35099-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="35099-153">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="35099-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="35099-154">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="35099-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="35099-155">Bindungen</span><span class="sxs-lookup"><span data-stu-id="35099-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="35099-156">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="35099-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="35099-157">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="35099-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
