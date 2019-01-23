---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555387"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="418b7-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="418b7-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="418b7-103">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="418b7-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="418b7-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="418b7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="418b7-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="418b7-105">\<behaviors></span></span>  
<span data-ttu-id="418b7-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="418b7-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="418b7-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="418b7-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="418b7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="418b7-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="418b7-109">Typ</span><span class="sxs-lookup"><span data-stu-id="418b7-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="418b7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="418b7-110">Attributes and elements</span></span>  
  
<span data-ttu-id="418b7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="418b7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="418b7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="418b7-112">Attributes</span></span>

| <span data-ttu-id="418b7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="418b7-113">Attribute</span></span>               | <span data-ttu-id="418b7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="418b7-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="418b7-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="418b7-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="418b7-116">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="418b7-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="418b7-117">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="418b7-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="418b7-118">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="418b7-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="418b7-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="418b7-119">Child elements</span></span>

<span data-ttu-id="418b7-120">Keine</span><span class="sxs-lookup"><span data-stu-id="418b7-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="418b7-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="418b7-121">Parent elements</span></span>

| <span data-ttu-id="418b7-122">Element</span><span class="sxs-lookup"><span data-stu-id="418b7-122">Element</span></span> | <span data-ttu-id="418b7-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="418b7-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="418b7-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="418b7-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="418b7-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="418b7-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="418b7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="418b7-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
