---
title: <transport> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 7328d67c4649010dce3e1c866238d1e0067e4990
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157069"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="fa145-102">\<transport> von \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="fa145-102">\<transport> of \<peerTransport></span></span>

<span data-ttu-id="fa145-103">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="fa145-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="fa145-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa145-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa145-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa145-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fa145-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa145-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa145-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="fa145-107">Attributes</span></span>  
  
|<span data-ttu-id="fa145-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fa145-108">Attribute</span></span>|<span data-ttu-id="fa145-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa145-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa145-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="fa145-110">credentialType</span></span>|<span data-ttu-id="fa145-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fa145-111">Optional.</span></span> <span data-ttu-id="fa145-112">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa145-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="fa145-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fa145-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="fa145-114">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="fa145-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="fa145-115">Wert</span><span class="sxs-lookup"><span data-stu-id="fa145-115">Value</span></span>|<span data-ttu-id="fa145-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa145-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa145-117">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="fa145-117">Certificate</span></span>|<span data-ttu-id="fa145-118">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa145-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="fa145-119">Kennwort</span><span class="sxs-lookup"><span data-stu-id="fa145-119">Password</span></span>|<span data-ttu-id="fa145-120">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa145-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa145-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa145-121">Child Elements</span></span>  

 <span data-ttu-id="fa145-122">Keine</span><span class="sxs-lookup"><span data-stu-id="fa145-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa145-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa145-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fa145-124">Element</span><span class="sxs-lookup"><span data-stu-id="fa145-124">Element</span></span>|<span data-ttu-id="fa145-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa145-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="fa145-126">Definiert die Sicherheitseinstellungen für einen Peertransport.</span><span class="sxs-lookup"><span data-stu-id="fa145-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa145-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fa145-127">Remarks</span></span>  

 <span data-ttu-id="fa145-128">Dieses Element wird nur festgelegt, wenn das Mode-Attribut von [\<security>](security-of-peertransport.md) auf oder festgelegt ist `Transport` `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="fa145-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa145-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa145-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fa145-130">Transport Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fa145-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="fa145-131">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="fa145-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="fa145-132">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="fa145-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="fa145-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa145-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fa145-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa145-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fa145-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa145-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
