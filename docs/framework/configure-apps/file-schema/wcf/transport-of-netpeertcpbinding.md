---
title: <transport> von <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735973"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="1a77b-102">\<transport> von \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="1a77b-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="1a77b-103">Gibt Einstellungen für die Sicherheit auf Transport Ebene an, wenn verwendet wird [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1a77b-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="1a77b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a77b-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a77b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1a77b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1a77b-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a77b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a77b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="1a77b-107">Attributes</span></span>  
  
|<span data-ttu-id="1a77b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1a77b-108">Attribute</span></span>|<span data-ttu-id="1a77b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a77b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a77b-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="1a77b-110">credentialType</span></span>|<span data-ttu-id="1a77b-111">(Optional)</span><span class="sxs-lookup"><span data-stu-id="1a77b-111">Optional.</span></span> <span data-ttu-id="1a77b-112">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a77b-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="1a77b-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1a77b-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="1a77b-114">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="1a77b-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="1a77b-115">Wert</span><span class="sxs-lookup"><span data-stu-id="1a77b-115">Value</span></span>|<span data-ttu-id="1a77b-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a77b-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1a77b-117">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="1a77b-117">Certificate</span></span>|<span data-ttu-id="1a77b-118">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a77b-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="1a77b-119">Kennwort</span><span class="sxs-lookup"><span data-stu-id="1a77b-119">Password</span></span>|<span data-ttu-id="1a77b-120">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a77b-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a77b-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a77b-121">Child Elements</span></span>  
 <span data-ttu-id="1a77b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="1a77b-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a77b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a77b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1a77b-124">Element</span><span class="sxs-lookup"><span data-stu-id="1a77b-124">Element</span></span>|<span data-ttu-id="1a77b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a77b-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="1a77b-126">Definiert die Sicherheitseinstellungen für [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1a77b-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a77b-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a77b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="1a77b-128">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1a77b-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1a77b-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1a77b-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1a77b-130">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="1a77b-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1a77b-131">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1a77b-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
