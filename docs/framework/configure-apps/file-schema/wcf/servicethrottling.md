---
title: '&lt;serviceThrottling&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aea9702b5376e584c9598be1a6270dbe0cc4c717
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicethrottlinggt"></a><span data-ttu-id="f7e33-102">&lt;serviceThrottling&gt;</span><span class="sxs-lookup"><span data-stu-id="f7e33-102">&lt;serviceThrottling&gt;</span></span>
<span data-ttu-id="f7e33-103">Legt den Einschränkungsmechanismus eines WCF (Windows Communication Foundation)-Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="f7e33-103">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="f7e33-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f7e33-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f7e33-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f7e33-105">\<behaviors></span></span>  
<span data-ttu-id="f7e33-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f7e33-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f7e33-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f7e33-107">\<behavior></span></span>  
<span data-ttu-id="f7e33-108">\<ServiceThrottling ></span><span class="sxs-lookup"><span data-stu-id="f7e33-108">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e33-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7e33-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7e33-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f7e33-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f7e33-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7e33-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7e33-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f7e33-112">Attributes</span></span>  
  
|<span data-ttu-id="f7e33-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f7e33-113">Attribute</span></span>|<span data-ttu-id="f7e33-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7e33-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7e33-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="f7e33-115">maxConcurrentCalls</span></span>|<span data-ttu-id="f7e33-116">Eine positive ganze Zahl, die die Anzahl von Nachrichten begrenzt, die gegenwärtig auf einem <xref:System.ServiceModel.ServiceHost> verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f7e33-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="f7e33-117">Aufrufe oberhalb des Limits werden in die Warteschlange gestellt.</span><span class="sxs-lookup"><span data-stu-id="f7e33-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="f7e33-118">Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="f7e33-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="f7e33-119">Der Standardwert ist 16 * Prozessoranzahl.</span><span class="sxs-lookup"><span data-stu-id="f7e33-119">The default is 16 * processor count.</span></span>|  
|<span data-ttu-id="f7e33-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="f7e33-120">maxConcurrentInstances</span></span>|<span data-ttu-id="f7e33-121">Eine positive ganze Zahl, die die Anzahl von <xref:System.ServiceModel.InstanceContext>-Objekten begrenzt , die gleichzeitig auf einem <xref:System.ServiceModel.ServiceHost> ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7e33-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="f7e33-122">Fordert das Erstellen zusätzlicher Instanzen an, die in eine Warteschlange eingereiht und abgeschlossen werden, wenn ein Slot unterhalb des Limits verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="f7e33-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="f7e33-123">Der Standardwert entspricht der Summe von maxConcurrentSessions und MaxConcurrentCalls.</span><span class="sxs-lookup"><span data-stu-id="f7e33-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="f7e33-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="f7e33-124">maxConcurrentSessions</span></span>|<span data-ttu-id="f7e33-125">Eine positive ganze Zahl, die die Anzahl von Sitzungen begrenzt, die ein <xref:System.ServiceModel.ServiceHost>-Objekt akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="f7e33-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="f7e33-126">Der Dienst akzeptiert Verbindungen über diesen Grenzwert hinaus, doch nur die Kanäle unter dem Grenzwert sind aktiv (Nachrichten werden von dem Kanal gelesen).</span><span class="sxs-lookup"><span data-stu-id="f7e33-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="f7e33-127">Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="f7e33-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="f7e33-128">Der Standardwert ist 100 * Prozessoranzahl.</span><span class="sxs-lookup"><span data-stu-id="f7e33-128">The default is 100 * processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7e33-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7e33-129">Child Elements</span></span>  
 <span data-ttu-id="f7e33-130">Keine</span><span class="sxs-lookup"><span data-stu-id="f7e33-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7e33-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f7e33-131">Parent Elements</span></span>  
  
|<span data-ttu-id="f7e33-132">Element</span><span class="sxs-lookup"><span data-stu-id="f7e33-132">Element</span></span>|<span data-ttu-id="f7e33-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7e33-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7e33-134">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f7e33-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f7e33-135">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="f7e33-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7e33-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7e33-136">Remarks</span></span>  
 <span data-ttu-id="f7e33-137">Mit der Einschränkung wird die Anzahl gleichzeitiger Aufrufe, Instanzen oder Sitzungen begrenzt, um eine übermäßige Ressourcenbeanspruchung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f7e33-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="f7e33-138">Eine Ablaufverfolgung wird jedes Mal geschrieben, wenn der Wert von Attributen erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="f7e33-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="f7e33-139">Die erste Ablaufverfolgung wird als Warnung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7e33-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7e33-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7e33-140">Example</span></span>  
 <span data-ttu-id="f7e33-141">Im folgenden Konfigurationsbeispiel beschränkt der Dienst die maximale Anzahl gleichzeitiger Aufrufe auf 2 und die maximale Anzahl gleichzeitiger Instanzen auf 10.</span><span class="sxs-lookup"><span data-stu-id="f7e33-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="f7e33-142">Ein ausführlicheres Beispiel für die Ausführung dieses Beispiels finden Sie unter [Einschränkung](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="f7e33-142">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>   
  <serviceBehaviors>   
    <behavior name="CalculatorServiceBehavior">   
      <serviceDebug includeExceptionDetailInFaults="False" />   
      <serviceMetadata httpGetEnabled="True"/>   
      <!-- Specify throttling behavior -->  
      <serviceThrottling maxConcurrentCalls="2"   
           maxConcurrentInstances="10"/>   
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7e33-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7e33-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>  
 [<span data-ttu-id="f7e33-144">Verwenden von ServiceThrottlingBehavior zur Steuerung der WCF-Dienst Performance</span><span class="sxs-lookup"><span data-stu-id="f7e33-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
