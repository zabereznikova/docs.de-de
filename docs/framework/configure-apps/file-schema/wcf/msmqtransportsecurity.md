---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 9d28f3f08e9c3984c055567df03f2839709a1522
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204644"
---
# \<msmqTransportSecurity>

<span data-ttu-id="40bc2-101">Gibt die MSMQ-Transportsicherheitseinstellungen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="40bc2-101">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="40bc2-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="40bc2-102">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40bc2-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="40bc2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="40bc2-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="40bc2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40bc2-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="40bc2-105">Attributes</span></span>  
  
|<span data-ttu-id="40bc2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="40bc2-106">Attribute</span></span>|<span data-ttu-id="40bc2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40bc2-107">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="40bc2-108">Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="40bc2-108">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="40bc2-109">Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="40bc2-109">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="40bc2-110">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="40bc2-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="40bc2-111">-None: keine Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="40bc2-111">-   None: No authentication.</span></span><br /><span data-ttu-id="40bc2-112">-Windows: der Authentifizierungsmechanismus verwendet Active Directory, um das X. 509-Zertifikat für die SID, die der Nachricht zugeordnet ist, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="40bc2-112">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="40bc2-113">Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.</span><span class="sxs-lookup"><span data-stu-id="40bc2-113">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="40bc2-114">-Certificate: der Kanal Ruft das Zertifikat aus dem Zertifikat Speicher ab.</span><span class="sxs-lookup"><span data-stu-id="40bc2-114">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="40bc2-115">Der Standardwert lautet Windows.</span><span class="sxs-lookup"><span data-stu-id="40bc2-115">The default value is Windows.</span></span> <span data-ttu-id="40bc2-116">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="40bc2-116">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="40bc2-117">Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40bc2-117">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="40bc2-118">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="40bc2-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="40bc2-119">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="40bc2-119">-   RC4Stream</span></span><br /><span data-ttu-id="40bc2-120">-AES</span><span class="sxs-lookup"><span data-stu-id="40bc2-120">-   AES</span></span><br /><br /> <span data-ttu-id="40bc2-121">Der Standardwert ist RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="40bc2-121">The default value is RC4Stream.</span></span> <span data-ttu-id="40bc2-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="40bc2-122">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="40bc2-123">Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="40bc2-123">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="40bc2-124">Die Verschlüsselung gewährleistet die Nachrichten Integrität, während "verschlüsselungssign" sowohl Nachrichten Integrität als auch Nichtabstreitbarkeit sicherstellt Das heißt, die Nachricht stammt tatsächlich vom Absender, und der Absender ist die Person, die Sie sagen.</span><span class="sxs-lookup"><span data-stu-id="40bc2-124">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="40bc2-125">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="40bc2-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="40bc2-126">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="40bc2-126">-   None: No protection.</span></span><br /><span data-ttu-id="40bc2-127">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="40bc2-127">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="40bc2-128">-Verschlüsseltandsign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="40bc2-128">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="40bc2-129">Der Standardwert ist Sign.</span><span class="sxs-lookup"><span data-stu-id="40bc2-129">The default value is Sign.</span></span> <span data-ttu-id="40bc2-130">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="40bc2-130">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="40bc2-131">Gibt den Algorithmus an, der beim Berechnen des Hashwerts als Teil von Signaturen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40bc2-131">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="40bc2-132">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="40bc2-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="40bc2-133">-MD5</span><span class="sxs-lookup"><span data-stu-id="40bc2-133">-   MD5</span></span><br /><span data-ttu-id="40bc2-134">-SHA1</span><span class="sxs-lookup"><span data-stu-id="40bc2-134">-   SHA1</span></span><br /><span data-ttu-id="40bc2-135">-SHA256</span><span class="sxs-lookup"><span data-stu-id="40bc2-135">-   SHA256</span></span><br /><span data-ttu-id="40bc2-136">-SHA512</span><span class="sxs-lookup"><span data-stu-id="40bc2-136">-   SHA512</span></span><br /><br /> <span data-ttu-id="40bc2-137">Der Standardwert ist SHA1.</span><span class="sxs-lookup"><span data-stu-id="40bc2-137">The default value is SHA1.</span></span> <span data-ttu-id="40bc2-138">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="40bc2-138">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="40bc2-139">Aufgrund von Konnektivitätsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="40bc2-139">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40bc2-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40bc2-140">Child Elements</span></span>  

 <span data-ttu-id="40bc2-141">Keine</span><span class="sxs-lookup"><span data-stu-id="40bc2-141">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40bc2-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40bc2-142">Parent Elements</span></span>  
  
|<span data-ttu-id="40bc2-143">Element</span><span class="sxs-lookup"><span data-stu-id="40bc2-143">Element</span></span>|<span data-ttu-id="40bc2-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40bc2-144">Description</span></span>|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|<span data-ttu-id="40bc2-145">Gibt die Einstellungen an, die für die Interaktion mit einem Message Queuing (MSMQ)-Absender oder -Empfänger erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="40bc2-145">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[\<msmqTransport>](msmqtransport.md)|<span data-ttu-id="40bc2-146">Gibt die Eigenschaften der Warteschlangenkommunikation für einen Windows Communication Foundation (WCF)-Dienst an, der das systemeigene Message Queuing (MSMQ)-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="40bc2-146">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40bc2-147">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="40bc2-147">Remarks</span></span>  

 <span data-ttu-id="40bc2-148">Weitere Informationen zur Transportsicherheit finden Sie unter [Transportsicherheit](../../../wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="40bc2-148">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bc2-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40bc2-149">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="40bc2-150">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="40bc2-150">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="40bc2-151">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="40bc2-151">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="40bc2-152">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="40bc2-152">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="40bc2-153">Bindungen</span><span class="sxs-lookup"><span data-stu-id="40bc2-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="40bc2-154">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="40bc2-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="40bc2-155">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="40bc2-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="40bc2-156">Transport Sicherheit</span><span class="sxs-lookup"><span data-stu-id="40bc2-156">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
