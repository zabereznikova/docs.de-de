---
title: <synchronousReceive>-Element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 2073d115dd87d513a6e48b8b585fed4b49d5bb32
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157173"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="6b890-102">\<synchronousReceive>-Element</span><span class="sxs-lookup"><span data-stu-id="6b890-102">\<synchronousReceive> element</span></span>

<span data-ttu-id="6b890-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b890-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="6b890-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="6b890-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="6b890-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b890-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b890-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b890-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6b890-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b890-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b890-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b890-108">Attributes</span></span>  

 <span data-ttu-id="6b890-109">Keine</span><span class="sxs-lookup"><span data-stu-id="6b890-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b890-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b890-110">Child Elements</span></span>  

 <span data-ttu-id="6b890-111">Keine</span><span class="sxs-lookup"><span data-stu-id="6b890-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b890-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b890-112">Parent Elements</span></span>  
  
|<span data-ttu-id="6b890-113">Element</span><span class="sxs-lookup"><span data-stu-id="6b890-113">Element</span></span>|<span data-ttu-id="6b890-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b890-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6b890-115">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="6b890-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b890-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6b890-116">Remarks</span></span>  

 <span data-ttu-id="6b890-117">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b890-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="6b890-118">Windows Communication Foundation (WCF) gibt für jeden akzeptierten Kanal einen neuen Thread für die Verschiebung aus.</span><span class="sxs-lookup"><span data-stu-id="6b890-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="6b890-119">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6b890-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b890-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b890-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
