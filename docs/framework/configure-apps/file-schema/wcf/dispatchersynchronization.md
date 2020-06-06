---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398004"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="f0221-101">Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f0221-101">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="f0221-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0221-102">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="f0221-103">type</span><span class="sxs-lookup"><span data-stu-id="f0221-103">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0221-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0221-104">Attributes and elements</span></span>  
  
<span data-ttu-id="f0221-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0221-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0221-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0221-106">Attributes</span></span>

| <span data-ttu-id="f0221-107">attribute</span><span class="sxs-lookup"><span data-stu-id="f0221-107">Attribute</span></span>               | <span data-ttu-id="f0221-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0221-108">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="f0221-109">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="f0221-109">asynchronousSendEnabled</span></span> | <span data-ttu-id="f0221-110">Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f0221-110">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="f0221-111">Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="f0221-111">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="f0221-112">Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f0221-112">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="f0221-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0221-113">Child elements</span></span>

<span data-ttu-id="f0221-114">Keine</span><span class="sxs-lookup"><span data-stu-id="f0221-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f0221-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0221-115">Parent elements</span></span>

| <span data-ttu-id="f0221-116">Element</span><span class="sxs-lookup"><span data-stu-id="f0221-116">Element</span></span> | <span data-ttu-id="f0221-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0221-117">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f0221-118">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="f0221-118">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f0221-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0221-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
