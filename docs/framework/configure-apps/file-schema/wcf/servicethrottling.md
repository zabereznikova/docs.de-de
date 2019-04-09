---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 995ff9979096757225c9241e977f86f755955945
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158768"
---
# <a name="servicethrottling"></a><span data-ttu-id="ceb05-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="ceb05-101">\<serviceThrottling></span></span>
<span data-ttu-id="ceb05-102">Legt den Einschränkungsmechanismus eines WCF (Windows Communication Foundation)-Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="ceb05-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="ceb05-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ceb05-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ceb05-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ceb05-104">\<behaviors></span></span>  
<span data-ttu-id="ceb05-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ceb05-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ceb05-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ceb05-106">\<behavior></span></span>  
<span data-ttu-id="ceb05-107">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="ceb05-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb05-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ceb05-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ceb05-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ceb05-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ceb05-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ceb05-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ceb05-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ceb05-111">Attributes</span></span>  
  
|<span data-ttu-id="ceb05-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ceb05-112">Attribute</span></span>|<span data-ttu-id="ceb05-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceb05-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ceb05-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="ceb05-114">maxConcurrentCalls</span></span>|<span data-ttu-id="ceb05-115">Eine positive ganze Zahl, die die Anzahl von Nachrichten begrenzt, die gegenwärtig auf einem <xref:System.ServiceModel.ServiceHost> verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ceb05-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="ceb05-116">Aufrufe oberhalb des Limits werden in die Warteschlange gestellt.</span><span class="sxs-lookup"><span data-stu-id="ceb05-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="ceb05-117">Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="ceb05-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="ceb05-118">Der Standardwert ist 16 \* Prozessoranzahl.</span><span class="sxs-lookup"><span data-stu-id="ceb05-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="ceb05-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="ceb05-119">maxConcurrentInstances</span></span>|<span data-ttu-id="ceb05-120">Eine positive ganze Zahl, die die Anzahl von <xref:System.ServiceModel.InstanceContext>-Objekten begrenzt , die gleichzeitig auf einem <xref:System.ServiceModel.ServiceHost> ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ceb05-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="ceb05-121">Fordert das Erstellen zusätzlicher Instanzen an, die in eine Warteschlange eingereiht und abgeschlossen werden, wenn ein Slot unterhalb des Limits verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="ceb05-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="ceb05-122">Der Standardwert entspricht der Summe von maxConcurrentSessions und MaxConcurrentCalls.</span><span class="sxs-lookup"><span data-stu-id="ceb05-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="ceb05-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="ceb05-123">maxConcurrentSessions</span></span>|<span data-ttu-id="ceb05-124">Eine positive ganze Zahl, die die Anzahl von Sitzungen begrenzt, die ein <xref:System.ServiceModel.ServiceHost>-Objekt akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="ceb05-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="ceb05-125">Der Dienst akzeptiert Verbindungen über diesen Grenzwert hinaus, doch nur die Kanäle unter dem Grenzwert sind aktiv (Nachrichten werden von dem Kanal gelesen).</span><span class="sxs-lookup"><span data-stu-id="ceb05-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="ceb05-126">Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="ceb05-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="ceb05-127">Der Standardwert ist 100 \* Prozessoranzahl.</span><span class="sxs-lookup"><span data-stu-id="ceb05-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ceb05-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ceb05-128">Child Elements</span></span>  
 <span data-ttu-id="ceb05-129">Keine</span><span class="sxs-lookup"><span data-stu-id="ceb05-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ceb05-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ceb05-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ceb05-131">Element</span><span class="sxs-lookup"><span data-stu-id="ceb05-131">Element</span></span>|<span data-ttu-id="ceb05-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceb05-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ceb05-133">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ceb05-133">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ceb05-134">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="ceb05-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceb05-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ceb05-135">Remarks</span></span>  
 <span data-ttu-id="ceb05-136">Mit der Einschränkung wird die Anzahl gleichzeitiger Aufrufe, Instanzen oder Sitzungen begrenzt, um eine übermäßige Ressourcenbeanspruchung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ceb05-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="ceb05-137">Eine Ablaufverfolgung wird jedes Mal geschrieben, wenn der Wert von Attributen erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="ceb05-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="ceb05-138">Die erste Ablaufverfolgung wird als Warnung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ceb05-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ceb05-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ceb05-139">Example</span></span>  
 <span data-ttu-id="ceb05-140">Im folgenden Konfigurationsbeispiel beschränkt der Dienst die maximale Anzahl gleichzeitiger Aufrufe auf 2 und die maximale Anzahl gleichzeitiger Instanzen auf 10.</span><span class="sxs-lookup"><span data-stu-id="ceb05-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="ceb05-141">Ein ausführliches Beispiel zum Ausführen dieses Beispiels finden Sie unter [Drosselung](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="ceb05-141">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ceb05-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceb05-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="ceb05-143">Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="ceb05-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
