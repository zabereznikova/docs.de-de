---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925843"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="8cee1-101">\<dispatchersynchronisierungs-></span><span class="sxs-lookup"><span data-stu-id="8cee1-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="8cee1-102">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8cee1-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="8cee1-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8cee1-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8cee1-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8cee1-104">\<behaviors></span></span>  
<span data-ttu-id="8cee1-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8cee1-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="8cee1-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8cee1-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cee1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cee1-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="8cee1-108">Typ</span><span class="sxs-lookup"><span data-stu-id="8cee1-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cee1-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8cee1-109">Attributes and elements</span></span>  
  
<span data-ttu-id="8cee1-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8cee1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cee1-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8cee1-111">Attributes</span></span>

| <span data-ttu-id="8cee1-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="8cee1-112">Attribute</span></span>               | <span data-ttu-id="8cee1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cee1-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="8cee1-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="8cee1-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="8cee1-115">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8cee1-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="8cee1-116">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="8cee1-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="8cee1-117">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="8cee1-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="8cee1-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8cee1-118">Child elements</span></span>

<span data-ttu-id="8cee1-119">Keine</span><span class="sxs-lookup"><span data-stu-id="8cee1-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8cee1-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8cee1-120">Parent elements</span></span>

| <span data-ttu-id="8cee1-121">Element</span><span class="sxs-lookup"><span data-stu-id="8cee1-121">Element</span></span> | <span data-ttu-id="8cee1-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cee1-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="8cee1-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8cee1-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8cee1-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="8cee1-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8cee1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cee1-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
