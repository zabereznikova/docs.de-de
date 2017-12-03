---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0a6349f50c8810d834d7887daecb6ac9cffb2e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="590d9-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="590d9-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="590d9-103">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="590d9-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="590d9-104">\<system.serviceModel > \<Verhalten > \<EndpointBehaviors > \<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="590d9-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="590d9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="590d9-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="590d9-106">Typ</span><span class="sxs-lookup"><span data-stu-id="590d9-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="590d9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="590d9-107">Attributes and elements</span></span>

<span data-ttu-id="590d9-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="590d9-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="590d9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="590d9-109">Attributes</span></span>

| <span data-ttu-id="590d9-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="590d9-110">Attribute</span></span>               | <span data-ttu-id="590d9-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="590d9-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="590d9-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="590d9-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="590d9-113">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="590d9-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="590d9-114">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="590d9-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="590d9-115">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="590d9-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="590d9-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="590d9-116">Child elements</span></span>

<span data-ttu-id="590d9-117">Keine</span><span class="sxs-lookup"><span data-stu-id="590d9-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="590d9-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="590d9-118">Parent elements</span></span>

| <span data-ttu-id="590d9-119">Element</span><span class="sxs-lookup"><span data-stu-id="590d9-119">Element</span></span> | <span data-ttu-id="590d9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="590d9-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="590d9-121">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="590d9-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="590d9-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="590d9-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="590d9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="590d9-123">See also</span></span>

 <span data-ttu-id="590d9-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="590d9-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
