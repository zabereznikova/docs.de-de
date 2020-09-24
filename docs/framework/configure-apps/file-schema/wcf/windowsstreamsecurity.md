---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 3c82bd81bd0fabf10f2dd835188b346f62d038b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167079"
---
# \<windowsStreamSecurity>

<span data-ttu-id="7bd08-101">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="7bd08-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="7bd08-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bd08-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bd08-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7bd08-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7bd08-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7bd08-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bd08-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="7bd08-105">Attributes</span></span>  
  
|<span data-ttu-id="7bd08-106">attribute</span><span class="sxs-lookup"><span data-stu-id="7bd08-106">Attribute</span></span>|<span data-ttu-id="7bd08-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bd08-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7bd08-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7bd08-108">protectionLevel</span></span>|<span data-ttu-id="7bd08-109">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="7bd08-109">Defines message-level security.</span></span> <span data-ttu-id="7bd08-110">Das Signieren von Nachrichten verringert das Risiko, dass Nachrichten während der Übertragung durch Dritte manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="7bd08-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="7bd08-111">Mit der Verschlüsselung können Daten während des Transports geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="7bd08-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="7bd08-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7bd08-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7bd08-113">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="7bd08-113">-   None: No protection.</span></span><br /><span data-ttu-id="7bd08-114">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="7bd08-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="7bd08-115">-Verschlüsseltandsign: Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7bd08-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="7bd08-116">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="7bd08-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="7bd08-117">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="7bd08-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bd08-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7bd08-118">Child Elements</span></span>  

 <span data-ttu-id="7bd08-119">Keine</span><span class="sxs-lookup"><span data-stu-id="7bd08-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bd08-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7bd08-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7bd08-121">Element</span><span class="sxs-lookup"><span data-stu-id="7bd08-121">Element</span></span>|<span data-ttu-id="7bd08-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bd08-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="7bd08-123">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="7bd08-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bd08-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7bd08-124">Remarks</span></span>  

 <span data-ttu-id="7bd08-125">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="7bd08-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="7bd08-126">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="7bd08-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="7bd08-127">Die Konfiguration dieser Transportsicherheit wird durch dieses Konfigurationselement und durch gekapselt [\<sslStreamSecurity>](sslstreamsecurity.md) , die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="7bd08-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd08-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bd08-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="7bd08-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7bd08-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7bd08-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="7bd08-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7bd08-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="7bd08-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
