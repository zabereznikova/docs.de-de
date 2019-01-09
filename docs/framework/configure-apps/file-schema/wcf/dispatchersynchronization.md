---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 86660620113b162a9a5260b7026a64455284d184
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151461"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="9ed67-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="9ed67-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="9ed67-103">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9ed67-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="9ed67-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ed67-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9ed67-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9ed67-105">\<behaviors></span></span>  
<span data-ttu-id="9ed67-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9ed67-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9ed67-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="9ed67-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed67-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ed67-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="9ed67-109">Typ</span><span class="sxs-lookup"><span data-stu-id="9ed67-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ed67-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9ed67-110">Attributes and elements</span></span>  
  
<span data-ttu-id="9ed67-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ed67-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ed67-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ed67-112">Attributes</span></span>

| <span data-ttu-id="9ed67-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9ed67-113">Attribute</span></span>               | <span data-ttu-id="9ed67-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ed67-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="9ed67-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="9ed67-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="9ed67-116">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9ed67-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="9ed67-117">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9ed67-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="9ed67-118">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="9ed67-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="9ed67-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ed67-119">Child elements</span></span>

<span data-ttu-id="9ed67-120">Keine</span><span class="sxs-lookup"><span data-stu-id="9ed67-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9ed67-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ed67-121">Parent elements</span></span>

| <span data-ttu-id="9ed67-122">Element</span><span class="sxs-lookup"><span data-stu-id="9ed67-122">Element</span></span> | <span data-ttu-id="9ed67-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ed67-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="9ed67-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9ed67-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9ed67-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="9ed67-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9ed67-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ed67-126">See also</span></span>

 <span data-ttu-id="9ed67-127"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="9ed67-127"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
