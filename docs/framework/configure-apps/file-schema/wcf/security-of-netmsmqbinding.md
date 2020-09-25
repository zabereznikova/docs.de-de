---
title: <security> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 32b066fdf4d8edbbd36fdff7b14bdec87ddc970d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170076"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="728c2-102">\<security> von \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="728c2-102">\<security> of \<netMsmqBinding></span></span>

<span data-ttu-id="728c2-103">Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.</span><span class="sxs-lookup"><span data-stu-id="728c2-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="728c2-104">Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="728c2-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="728c2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="728c2-105">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="728c2-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="728c2-106">Attributes and Elements</span></span>  

 <span data-ttu-id="728c2-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="728c2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="728c2-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="728c2-108">Attributes</span></span>  
  
|<span data-ttu-id="728c2-109">attribute</span><span class="sxs-lookup"><span data-stu-id="728c2-109">Attribute</span></span>|<span data-ttu-id="728c2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="728c2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="728c2-111">Modus</span><span class="sxs-lookup"><span data-stu-id="728c2-111">mode</span></span>|<span data-ttu-id="728c2-112">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert.</span><span class="sxs-lookup"><span data-stu-id="728c2-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="728c2-113">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="728c2-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="728c2-114">-None: Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="728c2-114">-   None: This disables security.</span></span><br /><span data-ttu-id="728c2-115">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="728c2-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="728c2-116">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="728c2-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="728c2-117">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="728c2-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="728c2-118">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="728c2-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="728c2-119">-Message: gibt die End-End-Anwendungssicherheit an.</span><span class="sxs-lookup"><span data-stu-id="728c2-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="728c2-120">Es wird keine Sicherheit auf Transportebene bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="728c2-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="728c2-121">Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="728c2-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="728c2-122">-Both: bietet Sicherheit auf Transport-und SOAP-Messaging Ebene.</span><span class="sxs-lookup"><span data-stu-id="728c2-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="728c2-123">Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="728c2-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="728c2-124">Der Standardwert ist Transport.</span><span class="sxs-lookup"><span data-stu-id="728c2-124">The default value is Transport.</span></span> <span data-ttu-id="728c2-125">Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="728c2-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="728c2-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="728c2-126">Child Elements</span></span>  
  
|<span data-ttu-id="728c2-127">Element</span><span class="sxs-lookup"><span data-stu-id="728c2-127">Element</span></span>|<span data-ttu-id="728c2-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="728c2-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="728c2-129">Definiert die SOAP-Nachrichtensicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="728c2-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="728c2-130">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="728c2-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="728c2-131">Definiert die Sicherheitseinstellungen für den MSMQ-Transport.</span><span class="sxs-lookup"><span data-stu-id="728c2-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="728c2-132">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="728c2-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="728c2-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="728c2-133">Parent Elements</span></span>  
  
|<span data-ttu-id="728c2-134">Element</span><span class="sxs-lookup"><span data-stu-id="728c2-134">Element</span></span>|<span data-ttu-id="728c2-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="728c2-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="728c2-136">binding</span><span class="sxs-lookup"><span data-stu-id="728c2-136">binding</span></span>|<span data-ttu-id="728c2-137">Das Bindungs Element des [\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="728c2-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="728c2-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="728c2-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="728c2-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="728c2-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="728c2-140">Bindungen</span><span class="sxs-lookup"><span data-stu-id="728c2-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="728c2-141">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="728c2-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="728c2-142">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="728c2-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="728c2-143">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="728c2-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
