---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 6be9752e8102a5d4db4fed31aae8ff6d56fdd24e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673406"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="3534f-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="3534f-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="3534f-102">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3534f-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="3534f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3534f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="3534f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3534f-104">\<behaviors></span></span>  
<span data-ttu-id="3534f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3534f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="3534f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3534f-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3534f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3534f-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="3534f-108">Typ</span><span class="sxs-lookup"><span data-stu-id="3534f-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3534f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3534f-109">Attributes and elements</span></span>  
  
<span data-ttu-id="3534f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3534f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3534f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3534f-111">Attributes</span></span>

| <span data-ttu-id="3534f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="3534f-112">Attribute</span></span>               | <span data-ttu-id="3534f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3534f-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="3534f-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="3534f-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="3534f-115">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3534f-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="3534f-116">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="3534f-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="3534f-117">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="3534f-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3534f-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3534f-118">Child elements</span></span>

<span data-ttu-id="3534f-119">Keine</span><span class="sxs-lookup"><span data-stu-id="3534f-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3534f-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3534f-120">Parent elements</span></span>

| <span data-ttu-id="3534f-121">Element</span><span class="sxs-lookup"><span data-stu-id="3534f-121">Element</span></span> | <span data-ttu-id="3534f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3534f-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="3534f-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3534f-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3534f-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="3534f-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3534f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3534f-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
