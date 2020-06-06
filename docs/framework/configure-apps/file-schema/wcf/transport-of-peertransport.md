---
title: <transport> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399288"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="97a48-102">\<transport> von \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="97a48-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="97a48-103">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="97a48-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="97a48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97a48-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97a48-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="97a48-105">Attributes and Elements</span></span>  
 <span data-ttu-id="97a48-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="97a48-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97a48-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="97a48-107">Attributes</span></span>  
  
|<span data-ttu-id="97a48-108">attribute</span><span class="sxs-lookup"><span data-stu-id="97a48-108">Attribute</span></span>|<span data-ttu-id="97a48-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97a48-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97a48-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="97a48-110">credentialType</span></span>|<span data-ttu-id="97a48-111">(Optional)</span><span class="sxs-lookup"><span data-stu-id="97a48-111">Optional.</span></span> <span data-ttu-id="97a48-112">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97a48-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="97a48-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="97a48-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="97a48-114">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="97a48-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="97a48-115">Wert</span><span class="sxs-lookup"><span data-stu-id="97a48-115">Value</span></span>|<span data-ttu-id="97a48-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97a48-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="97a48-117">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="97a48-117">Certificate</span></span>|<span data-ttu-id="97a48-118">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97a48-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="97a48-119">Kennwort</span><span class="sxs-lookup"><span data-stu-id="97a48-119">Password</span></span>|<span data-ttu-id="97a48-120">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97a48-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97a48-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97a48-121">Child Elements</span></span>  
 <span data-ttu-id="97a48-122">Keine</span><span class="sxs-lookup"><span data-stu-id="97a48-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97a48-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97a48-123">Parent Elements</span></span>  
  
|<span data-ttu-id="97a48-124">Element</span><span class="sxs-lookup"><span data-stu-id="97a48-124">Element</span></span>|<span data-ttu-id="97a48-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97a48-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="97a48-126">Definiert die Sicherheitseinstellungen für einen Peertransport.</span><span class="sxs-lookup"><span data-stu-id="97a48-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97a48-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="97a48-127">Remarks</span></span>  
 <span data-ttu-id="97a48-128">Dieses Element wird nur festgelegt, wenn das Mode-Attribut von [\<security>](security-of-peertransport.md) auf oder festgelegt ist `Transport` `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="97a48-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a48-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97a48-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="97a48-130">Transport Sicherheit</span><span class="sxs-lookup"><span data-stu-id="97a48-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="97a48-131">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="97a48-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="97a48-132">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="97a48-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="97a48-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="97a48-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="97a48-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="97a48-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="97a48-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="97a48-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
