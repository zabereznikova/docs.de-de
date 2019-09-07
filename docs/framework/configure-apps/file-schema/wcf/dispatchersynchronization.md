---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398004"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="dc3dd-101">\<dispatchersynchronisierungs-></span><span class="sxs-lookup"><span data-stu-id="dc3dd-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="dc3dd-102">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="dc3dd-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="dc3dd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc3dd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc3dd-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dc3dd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dc3dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="dc3dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="dc3dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="dc3dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="dc3dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="dc3dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="dc3dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dispatchersynchronisierungs->**</span><span class="sxs-lookup"><span data-stu-id="dc3dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc3dd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc3dd-109">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="dc3dd-110">Typ</span><span class="sxs-lookup"><span data-stu-id="dc3dd-110">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc3dd-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc3dd-111">Attributes and elements</span></span>  
  
<span data-ttu-id="dc3dd-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc3dd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc3dd-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc3dd-113">Attributes</span></span>

| <span data-ttu-id="dc3dd-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc3dd-114">Attribute</span></span>               | <span data-ttu-id="dc3dd-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc3dd-115">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="dc3dd-116">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="dc3dd-116">asynchronousSendEnabled</span></span> | <span data-ttu-id="dc3dd-117">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc3dd-117">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="dc3dd-118">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="dc3dd-118">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="dc3dd-119">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="dc3dd-119">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="dc3dd-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc3dd-120">Child elements</span></span>

<span data-ttu-id="dc3dd-121">Keine</span><span class="sxs-lookup"><span data-stu-id="dc3dd-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dc3dd-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc3dd-122">Parent elements</span></span>

| <span data-ttu-id="dc3dd-123">Element</span><span class="sxs-lookup"><span data-stu-id="dc3dd-123">Element</span></span> | <span data-ttu-id="dc3dd-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc3dd-124">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="dc3dd-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dc3dd-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="dc3dd-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="dc3dd-126">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="dc3dd-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc3dd-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
