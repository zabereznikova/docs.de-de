---
title: Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ead2990285f10400cfae11c21bce76a5b6c362f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a><span data-ttu-id="dd8a7-102">Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="dd8a7-102">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>
<span data-ttu-id="dd8a7-103">Mit der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>-Klasse werden Eigenschaften verfügbar gemacht, mit denen die Anzahl der Instanzen oder Sitzungen begrenzt wird, die auf Anwendungsebene erstellt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-103">The <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class exposes properties that you can use to limit how many instances or sessions are created at the application level.</span></span> <span data-ttu-id="dd8a7-104">Mit diesem Verhalten kann die Leistung der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-104">Using this behavior, you can fine-tune the performance of your [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span>  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a><span data-ttu-id="dd8a7-105">Steuern von Dienstinstanzen und gleichzeitigen Aufrufen</span><span class="sxs-lookup"><span data-stu-id="dd8a7-105">Controlling Service Instances and Concurrent Calls</span></span>  
 <span data-ttu-id="dd8a7-106">Verwenden Sie die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>-Eigenschaft, um die maximale Anzahl der Nachrichten anzugeben, die aktiv in einer <xref:System.ServiceModel.ServiceHost>-Klasse verarbeitet werden und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft, um die maximale Anzahl der <xref:System.ServiceModel.InstanceContext>-Objekte im Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-106">Use the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> property to specify the maximum number of messages actively processing across a <xref:System.ServiceModel.ServiceHost> class, and the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> property to specify the maximum number of <xref:System.ServiceModel.InstanceContext> objects in the service.</span></span>  
  
 <span data-ttu-id="dd8a7-107">Da bestimmen die Einstellungen für diese Eigenschaften in der Regel nach praktische Erfahrung Ausführen der Anwendung für stattfindet geladen wird, die Einstellungen für die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Eigenschaften ist in der Regel angegeben, in einer Anwendungskonfigurationsdatei mithilfe der [ \<ServiceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) Element.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-107">Because determining the settings for these properties usually takes place after real-world experience running the application against loads, the settings for the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> properties is typically specified in an application configuration file using the [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) element.</span></span>  
  
 <span data-ttu-id="dd8a7-108">Im folgenden Codebeispiel wird die Verwendung der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>-Klasse von einer Anwendungskonfigurationsdatei gezeigt, die die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>-Eigenschaft und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft in einem einfachen Beispiel auf 1 festlegt.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-108">The following code example shows the use of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class from an application configuration file that sets the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> properties to 1 as a trivial example.</span></span> <span data-ttu-id="dd8a7-109">Die optimalen Einstellungen für eine bestimmte Anwendung finden Sie durch praktische Erfahrung heraus.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-109">Real-world experience determines the optimal settings for any particular application.</span></span>  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 <span data-ttu-id="dd8a7-110">Das genaue Laufzeitverhalten hängt von den Werten der <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft ab, mit denen die Anzahl der gleichzeitig in einem Vorgang ausführbaren Nachrichten und die Lebensdauer des Dienst-<xref:System.ServiceModel.InstanceContext> relativ zu den eingehenden Kanalsitzungen bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-110">The exact run-time behavior depends upon the values of the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> and <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> properties, which control how many messages can execute inside an operation at once and the lifetimes of the service <xref:System.ServiceModel.InstanceContext> relative to incoming channel sessions, respectively.</span></span>  
  
 <span data-ttu-id="dd8a7-111">Ausführliche Informationen finden Sie unter <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> und <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd8a7-111">For details, see <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd8a7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd8a7-112">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
