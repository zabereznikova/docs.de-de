---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 0c6d844ac287037b7a546d3a48e7cd924e8a63d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153611"
---
# \<serviceThrottling>

<span data-ttu-id="c84ec-101">Legt den Einschränkungsmechanismus eines WCF (Windows Communication Foundation)-Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="c84ec-101">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="c84ec-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="c84ec-102">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c84ec-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c84ec-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c84ec-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c84ec-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c84ec-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="c84ec-105">Attributes</span></span>  
  
|<span data-ttu-id="c84ec-106">attribute</span><span class="sxs-lookup"><span data-stu-id="c84ec-106">Attribute</span></span>|<span data-ttu-id="c84ec-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c84ec-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c84ec-108">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="c84ec-108">maxConcurrentCalls</span></span>|<span data-ttu-id="c84ec-109">Eine positive ganze Zahl, die die Anzahl von Nachrichten begrenzt, die gegenwärtig auf einem <xref:System.ServiceModel.ServiceHost> verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c84ec-109">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c84ec-110">Aufrufe, die diese Grenze überschreiten, werden in die Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="c84ec-110">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="c84ec-111">Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c84ec-111">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="c84ec-112">Der Standardwert ist 16 \* Prozessoranzahl.</span><span class="sxs-lookup"><span data-stu-id="c84ec-112">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="c84ec-113">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="c84ec-113">maxConcurrentInstances</span></span>|<span data-ttu-id="c84ec-114">Eine positive ganze Zahl, die die Anzahl von <xref:System.ServiceModel.InstanceContext>-Objekten begrenzt , die gleichzeitig auf einem <xref:System.ServiceModel.ServiceHost> ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c84ec-114">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c84ec-115">Fordert das Erstellen zusätzlicher Instanzen an, die in eine Warteschlange eingereiht und abgeschlossen werden, wenn ein Slot unterhalb des Limits verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="c84ec-115">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="c84ec-116">Der Standardwert entspricht der Summe von maxConcurrentSessions und MaxConcurrentCalls.</span><span class="sxs-lookup"><span data-stu-id="c84ec-116">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="c84ec-117">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="c84ec-117">maxConcurrentSessions</span></span>|<span data-ttu-id="c84ec-118">Eine positive ganze Zahl, die die Anzahl von Sitzungen begrenzt, die ein <xref:System.ServiceModel.ServiceHost>-Objekt akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="c84ec-118">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="c84ec-119">Der Dienst akzeptiert Verbindungen über diesen Grenzwert hinaus, doch nur die Kanäle unter dem Grenzwert sind aktiv (Nachrichten werden von dem Kanal gelesen).</span><span class="sxs-lookup"><span data-stu-id="c84ec-119">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="c84ec-120">Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c84ec-120">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="c84ec-121">Der Standardwert ist 100 \* Prozessoranzahl.</span><span class="sxs-lookup"><span data-stu-id="c84ec-121">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c84ec-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c84ec-122">Child Elements</span></span>  

 <span data-ttu-id="c84ec-123">Keine</span><span class="sxs-lookup"><span data-stu-id="c84ec-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c84ec-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c84ec-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c84ec-125">Element</span><span class="sxs-lookup"><span data-stu-id="c84ec-125">Element</span></span>|<span data-ttu-id="c84ec-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c84ec-126">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c84ec-127">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="c84ec-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c84ec-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c84ec-128">Remarks</span></span>  

 <span data-ttu-id="c84ec-129">Mit der Einschränkung wird die Anzahl gleichzeitiger Aufrufe, Instanzen oder Sitzungen begrenzt, um eine übermäßige Ressourcenbeanspruchung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c84ec-129">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="c84ec-130">Eine Ablaufverfolgung wird jedes Mal geschrieben, wenn der Wert von Attributen erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="c84ec-130">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="c84ec-131">Die erste Ablaufverfolgung wird als Warnung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c84ec-131">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84ec-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c84ec-132">Example</span></span>  

 <span data-ttu-id="c84ec-133">Im folgenden Konfigurationsbeispiel beschränkt der Dienst die maximale Anzahl gleichzeitiger Aufrufe auf 2 und die maximale Anzahl gleichzeitiger Instanzen auf 10.</span><span class="sxs-lookup"><span data-stu-id="c84ec-133">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="c84ec-134">Ein ausführliches Beispiel für die Ausführung dieses Beispiels finden Sie unter [Drosselung](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="c84ec-134">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="c84ec-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c84ec-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="c84ec-136">Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="c84ec-136">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
