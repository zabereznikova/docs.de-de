---
title: <transport> von <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 03e6236d1e89f16a460860f5dffff19b7bed8a0a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169829"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="ddf1d-102">\<transport> von \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="ddf1d-102">\<transport> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="ddf1d-103">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="ddf1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddf1d-104">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddf1d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ddf1d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ddf1d-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddf1d-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="ddf1d-107">Attributes</span></span>  
  
|<span data-ttu-id="ddf1d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ddf1d-108">Attribute</span></span>|<span data-ttu-id="ddf1d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddf1d-109">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="ddf1d-110">Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-110">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="ddf1d-111">Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-111">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="ddf1d-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ddf1d-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ddf1d-113">-None: keine Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-113">-   None: No authentication.</span></span><br /><span data-ttu-id="ddf1d-114">-Windows Domain: der Authentifizierungsmechanismus verwendet Active Directory, um das X. 509-Zertifikat für die SID, die der Nachricht zugeordnet ist, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-114">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="ddf1d-115">Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-115">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="ddf1d-116">-Certificate: der Kanal Ruft das Zertifikat aus dem Zertifikat Speicher ab.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-116">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="ddf1d-117">Der Standardwert ist WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-117">The default value is WindowsDomain.</span></span> <span data-ttu-id="ddf1d-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-118">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="ddf1d-119">Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-119">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="ddf1d-120">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ddf1d-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ddf1d-121">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="ddf1d-121">-   RC4Stream</span></span><br /><span data-ttu-id="ddf1d-122">-AES</span><span class="sxs-lookup"><span data-stu-id="ddf1d-122">-   AES</span></span><br /><br /> <span data-ttu-id="ddf1d-123">Der Standardwert ist RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-123">The default value is RC4Stream.</span></span> <span data-ttu-id="ddf1d-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-124">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="ddf1d-125">Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-125">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="ddf1d-126">Die Verschlüsselung gewährleistet die Nachrichten Integrität, während "verschlüsselungssign" sowohl Nachrichten Integrität als auch Nichtabstreitbarkeit sicherstellt Das heißt, die Nachricht stammt tatsächlich vom Absender, und der Absender ist die Person, die Sie sagen.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-126">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span><br /><br /> <span data-ttu-id="ddf1d-127">-Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ddf1d-127">-   Valid values include the following:</span></span><br /><span data-ttu-id="ddf1d-128">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-128">-   None: No protection.</span></span><br /><span data-ttu-id="ddf1d-129">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-129">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ddf1d-130">-Verschlüsseltandsign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-130">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="ddf1d-131">Der Standardwert ist Sign.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-131">The default value is Sign.</span></span> <span data-ttu-id="ddf1d-132">Dieses Attribut ist vom Typ ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-132">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="ddf1d-133">: Gibt den Algorithmus an, der beim Berechnen des Digest als Teil von Signaturen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-133">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="ddf1d-134">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ddf1d-134">Valid values include the following:</span></span><br /><span data-ttu-id="ddf1d-135">-MD5</span><span class="sxs-lookup"><span data-stu-id="ddf1d-135">-   MD5</span></span><br /><span data-ttu-id="ddf1d-136">-SHA1</span><span class="sxs-lookup"><span data-stu-id="ddf1d-136">-   SHA1</span></span><br /><span data-ttu-id="ddf1d-137">-SHA256</span><span class="sxs-lookup"><span data-stu-id="ddf1d-137">-   SHA256</span></span><br /><span data-ttu-id="ddf1d-138">-SHA512</span><span class="sxs-lookup"><span data-stu-id="ddf1d-138">-   SHA512</span></span><br /><br /> <span data-ttu-id="ddf1d-139">Der Standardwert ist SHA1.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-139">The default value is SHA1.</span></span> <span data-ttu-id="ddf1d-140">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-140">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="ddf1d-141">Aufgrund von Konnektivitätsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-141">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddf1d-142">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddf1d-142">Child Elements</span></span>  

 <span data-ttu-id="ddf1d-143">Keine</span><span class="sxs-lookup"><span data-stu-id="ddf1d-143">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddf1d-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddf1d-144">Parent Elements</span></span>  
  
|<span data-ttu-id="ddf1d-145">Element</span><span class="sxs-lookup"><span data-stu-id="ddf1d-145">Element</span></span>|<span data-ttu-id="ddf1d-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddf1d-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="ddf1d-147">Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-147">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddf1d-148">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ddf1d-148">Remarks</span></span>  

 <span data-ttu-id="ddf1d-149">Dieses Element kapselt die Sicherheitseinstellungen für den Message Queuing-Integrationstransport ein.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-149">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="ddf1d-150">Die Einstellungen für die Message Queuing-Integration und Transporte in der Warteschlange sind die gleichen.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-150">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="ddf1d-151">Es ermöglicht das Festlegen des Authentifizierungsmodus, des Verschlüsselungsalgorithmus, des Secure Hash-Algorithmus sowie der Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="ddf1d-151">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf1d-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddf1d-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="ddf1d-153">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ddf1d-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ddf1d-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ddf1d-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ddf1d-155">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ddf1d-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ddf1d-156">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ddf1d-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
