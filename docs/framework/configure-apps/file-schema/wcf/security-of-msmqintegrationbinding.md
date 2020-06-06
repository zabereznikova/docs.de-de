---
title: <security> von <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738681"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="c99b4-102">\<security> von \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="c99b4-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="c99b4-103">Definiert die Transportsicherheitseinstellungen für den Message Queuing (MSMQ)-Integrationskanal.</span><span class="sxs-lookup"><span data-stu-id="c99b4-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="c99b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c99b4-104">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c99b4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c99b4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c99b4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c99b4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c99b4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="c99b4-107">Attributes</span></span>  
  
|<span data-ttu-id="c99b4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c99b4-108">Attribute</span></span>|<span data-ttu-id="c99b4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c99b4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c99b4-110">Modus</span><span class="sxs-lookup"><span data-stu-id="c99b4-110">mode</span></span>|<span data-ttu-id="c99b4-111">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung mit dem Message Queuing-Integrationskanal steuert.</span><span class="sxs-lookup"><span data-stu-id="c99b4-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="c99b4-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c99b4-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c99b4-113">-None: Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c99b4-113">-   None: This disables security.</span></span><br /><span data-ttu-id="c99b4-114">-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c99b4-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="c99b4-115">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="c99b4-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="c99b4-116">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="c99b4-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="c99b4-117">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="c99b4-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="c99b4-118">Der Standardwert ist `Transport`.</span><span class="sxs-lookup"><span data-stu-id="c99b4-118">The default value is `Transport`.</span></span> <span data-ttu-id="c99b4-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c99b4-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c99b4-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c99b4-120">Child Elements</span></span>  
  
|<span data-ttu-id="c99b4-121">Element</span><span class="sxs-lookup"><span data-stu-id="c99b4-121">Element</span></span>|<span data-ttu-id="c99b4-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c99b4-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="c99b4-123">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="c99b4-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="c99b4-124">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c99b4-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c99b4-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c99b4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c99b4-126">Element</span><span class="sxs-lookup"><span data-stu-id="c99b4-126">Element</span></span>|<span data-ttu-id="c99b4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c99b4-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c99b4-128">Das Bindungs Element von [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c99b4-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c99b4-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c99b4-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="c99b4-130">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="c99b4-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="c99b4-131">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c99b4-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c99b4-132">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c99b4-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c99b4-133">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c99b4-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c99b4-134">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c99b4-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
