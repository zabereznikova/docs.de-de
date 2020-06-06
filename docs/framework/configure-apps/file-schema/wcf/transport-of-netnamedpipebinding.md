---
title: <transport> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735951"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="b6a3b-102">\<transport> von \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="b6a3b-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="b6a3b-103">Definiert die Transportsicherheitseinstellungen für eine benannte Pipe.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="b6a3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6a3b-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6a3b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a3b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b6a3b-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6a3b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6a3b-107">Attributes</span></span>  
  
|<span data-ttu-id="b6a3b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b6a3b-108">Attribute</span></span>|<span data-ttu-id="b6a3b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b6a3b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6a3b-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="b6a3b-110">protectionLevel</span></span>|<span data-ttu-id="b6a3b-111">Definiert die Schutzebene der benannten Pipe.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="b6a3b-112">Das Signieren von Nachrichten verringert das Risiko, dass Nachrichten während der Übertragung durch Dritte manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="b6a3b-113">Mit der Verschlüsselung können Daten während des Transports geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="b6a3b-114">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b6a3b-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b6a3b-115">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-115">-   None: No protection.</span></span><br /><span data-ttu-id="b6a3b-116">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="b6a3b-117">-Verschlüsseltandsign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="b6a3b-118">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6a3b-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a3b-119">Child Elements</span></span>  
 <span data-ttu-id="b6a3b-120">Keine</span><span class="sxs-lookup"><span data-stu-id="b6a3b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6a3b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6a3b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b6a3b-122">Element</span><span class="sxs-lookup"><span data-stu-id="b6a3b-122">Element</span></span>|<span data-ttu-id="b6a3b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6a3b-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="b6a3b-124">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="b6a3b-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6a3b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6a3b-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="b6a3b-126">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b6a3b-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b6a3b-127">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b6a3b-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b6a3b-128">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b6a3b-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b6a3b-129">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b6a3b-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
