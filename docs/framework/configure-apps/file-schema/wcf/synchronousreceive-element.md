---
title: <synchronousReceive>-Element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399495"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="abce1-102">\<synchronousReceive>-Element</span><span class="sxs-lookup"><span data-stu-id="abce1-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="abce1-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="abce1-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="abce1-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="abce1-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="abce1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="abce1-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abce1-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="abce1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="abce1-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="abce1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abce1-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="abce1-108">Attributes</span></span>  
 <span data-ttu-id="abce1-109">Keine</span><span class="sxs-lookup"><span data-stu-id="abce1-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="abce1-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="abce1-110">Child Elements</span></span>  
 <span data-ttu-id="abce1-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="abce1-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abce1-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="abce1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="abce1-113">Element</span><span class="sxs-lookup"><span data-stu-id="abce1-113">Element</span></span>|<span data-ttu-id="abce1-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="abce1-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="abce1-115">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="abce1-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abce1-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="abce1-116">Remarks</span></span>  
 <span data-ttu-id="abce1-117">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="abce1-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="abce1-118">Windows Communication Foundation (WCF) gibt für jeden akzeptierten Kanal einen neuen Thread für die Verschiebung aus.</span><span class="sxs-lookup"><span data-stu-id="abce1-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="abce1-119">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="abce1-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abce1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abce1-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
