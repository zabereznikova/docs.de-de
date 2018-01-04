---
title: Hierarchisches Konfigurationsmodell
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf8e7b37b6430be1eed9bc037bfa06aeb825b866
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hierarchical-configuration-model"></a><span data-ttu-id="e6855-102">Hierarchisches Konfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="e6855-102">Hierarchical Configuration Model</span></span>
<span data-ttu-id="e6855-103">In diesem Beispiel wird veranschaulicht, wie eine Hierarchie von Konfigurationsdateien für Dienste implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e6855-103">This sample demonstrates how to implement a hierarchy of configuration files for services.</span></span> <span data-ttu-id="e6855-104">Es wird auch gezeigt, wie Bindungen, Dienstverhalten und Endpunktverhalten von höheren Ebenen in der Hierarchie geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="e6855-104">It also shows how bindings, service behaviors, and endpoint behaviors are inherited from higher levels in the hierarchy.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="e6855-105">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="e6855-105">Sample details</span></span>  
 <span data-ttu-id="e6855-106">Eine der Funktionen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] entwickelt wurden, besteht in der Verbesserung des hierarchischen Konfigurationsmodells.</span><span class="sxs-lookup"><span data-stu-id="e6855-106">One of the features developed for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] is the improvement in the hierarchical configuration model.</span></span> <span data-ttu-id="e6855-107">Ein hierarchisches Konfigurationsmodell ist z. B. das Modell, das von Machine.config -> Rootweb.config -> Web.config definiert wurde. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] werden die Bindungen und Verhaltensweisen, die in den oberen Ebenen der Konfigurationshierarchie definiert werden, zum Dienst ohne explizite Konfiguration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e6855-107">An example of a hierarchical configuration model would be the one defined by Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], those bindings and behaviors that are defined in upper levels in the configuration hierarchy are added to your services with no explicit configuration.</span></span> <span data-ttu-id="e6855-108">In diesem Beispiel wird gezeigt, wie die Dienstkonfiguration basierend auf Konfigurationselementen vereinfacht werden kann, die auf Computer- oder Anwendungsebene definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e6855-108">This sample shows how it is possible to simplify your service configuration by relying on configuration elements defined at the computer or the application level.</span></span>  
  
 <span data-ttu-id="e6855-109">Dieses Beispiel umfasst neun Dienste, die in drei Hierarchieebenen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e6855-109">This sample consists of nine services, defined in three levels of hierarchy.</span></span> <span data-ttu-id="e6855-110">`Service1` befindet sich auf der Stammebene.</span><span class="sxs-lookup"><span data-stu-id="e6855-110">`Service1` is at the root.</span></span> <span data-ttu-id="e6855-111">`Service2` und `Service3` erben die Standardelemente von `Service1`.</span><span class="sxs-lookup"><span data-stu-id="e6855-111">`Service2` and `Service3` inherit the default elements from `Service1`.</span></span> <span data-ttu-id="e6855-112">`Service4`, `Service5`, `Service6` und `Service7` werden auf einer dritten Ebene der Hierarchie definiert und erben die Standardelemente von `Service3`.</span><span class="sxs-lookup"><span data-stu-id="e6855-112">`Service4`, `Service5`, `Service6` and `Service7` are defined at a third level of the hierarchy, inheriting the default elements from `Service3`.</span></span> <span data-ttu-id="e6855-113">`Service10` und `Service11` befinden sich schließlich auf einer vierten Ebene der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="e6855-113">Finally `Service10` and `Service11` are at a fourth level of the hierarchy.</span></span>  
  
 <span data-ttu-id="e6855-114">Alle Dienste implementieren den `IDesc`-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e6855-114">All the services implement the `IDesc` contract.</span></span> <span data-ttu-id="e6855-115">Nachfolgend wird die Definition der `IDesc`-Schnittstelle mit den in dieser Schnittstelle verfügbar gemachten Methoden anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e6855-115">The following is the definition of the `IDesc` interface that shows the methods exposed in this interface.</span></span> <span data-ttu-id="e6855-116">Die `IDesc`-Schnittstelle wird in Service1.cs definiert.</span><span class="sxs-lookup"><span data-stu-id="e6855-116">The `IDesc` interface is defined in Service1.cs.</span></span>  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 <span data-ttu-id="e6855-117">Die Implementierung dieser Methoden durch die Dienste ist einfach.</span><span class="sxs-lookup"><span data-stu-id="e6855-117">The implementation of these methods by the services is straightforward.</span></span> <span data-ttu-id="e6855-118">`ListEndpoints` durchläuft alle Dienstendpunkte und gibt eine Liste aller Endpunkte des Diensts zurück.</span><span class="sxs-lookup"><span data-stu-id="e6855-118">`ListEndpoints` iterates through all the service endpoints and returns a list of all the endpoints that the service has.</span></span> <span data-ttu-id="e6855-119">`ListServiceBehaviors` durchläuft alle dem Dienst hinzugefügten Verhaltensweisen und gibt eine Liste mit allen dem Dienst zugeordneten Dienstverhaltensweisen zurück.</span><span class="sxs-lookup"><span data-stu-id="e6855-119">`ListServiceBehaviors` iterates through all the behaviors added to the service and returns the list of all the service behaviors associated with the service.</span></span> <span data-ttu-id="e6855-120">`ListEndpointBehaviors` verhält sich ähnlich wie `ListServiceBehaviors`, gibt jedoch eine Liste mit Verhaltensweisen von Endpunkten zurück.</span><span class="sxs-lookup"><span data-stu-id="e6855-120">`ListEndpointBehaviors` behaves in a similar way to `ListServiceBehaviors`, but it returns the list of endpoint behaviors instead.</span></span>  
  
 <span data-ttu-id="e6855-121">Diese Implementierung ermöglicht es, dass der Client die Anzahl der vom Dienst verfügbar gemachten Endpunkte und die dem Dienst hinzugefügten Verhaltensweisen und Endpunktverhaltensweisen kennt.</span><span class="sxs-lookup"><span data-stu-id="e6855-121">This implementation allows the client to know how many endpoints the service is exposing and which service behaviors and endpoint behaviors have been added to the service.</span></span> <span data-ttu-id="e6855-122">Der Client, der als Teil des Beispiels implementiert wurde, fügt allen Diensten in der Projektmappe einen Dienstverweis hinzu und zeigt diese Elemente für jeden der Dienste an.</span><span class="sxs-lookup"><span data-stu-id="e6855-122">The client that has been implemented as part of the sample adds a service reference to all the services in the solution and shows these elements for each one of the services.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="e6855-123">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6855-123">To use this sample</span></span>  
  
#### <a name="to-run-the-client"></a><span data-ttu-id="e6855-124">So führen Sie den Client aus</span><span class="sxs-lookup"><span data-stu-id="e6855-124">To run the client</span></span>  
  
1.  <span data-ttu-id="e6855-125">Öffnen Sie die Datei ConfigHierarchicalModel.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6855-125">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ConfigHierarchicalModel.sln file.</span></span>  
  
2.  <span data-ttu-id="e6855-126">Wenn das Clientprojekt nicht bereits als Startprojekt eingerichtet ist, führen Sie folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="e6855-126">The client project is not already set up as the start-up project, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="e6855-127">In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, und wählen Sie dann **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e6855-127">In **Solution Explorer**, right-click the solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="e6855-128">In **allgemeine Eigenschaften**Option **Startprojekt**, und klicken Sie dann auf **einzelnes Startprojekt**.</span><span class="sxs-lookup"><span data-stu-id="e6855-128">In **Common Properties**, select **Startup Project**, and then click **Single startup project**.</span></span>  
  
    3.  <span data-ttu-id="e6855-129">Aus der **einzelnes Startprojekt** Dropdownliste, wählen **Client**.</span><span class="sxs-lookup"><span data-stu-id="e6855-129">From the **Single startup project** drop-down, select **Client**.</span></span>  
  
    4.  <span data-ttu-id="e6855-130">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e6855-130">Click **OK** to close the dialog.</span></span>  
  
3.  <span data-ttu-id="e6855-131">Drücken Sie STRG+UMSCHALT+B, um das Beispiel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6855-131">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="e6855-132">Drücken Sie STRG + F5, um den Client auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e6855-132">To run the client, press Ctrl+F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6855-133">Wenn diese Schritte nicht funktionieren, stellen Sie mithilfe der folgenden Schritte sicher, dass die Umgebung ordnungsgemäß eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6855-133">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="e6855-134">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e6855-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="e6855-135">Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e6855-135">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="e6855-136">Um das Beispiel in einer einzelnen oder Konfigurationen mit mehreren Computern ausführen, befolgen Sie die Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e6855-136">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6855-137">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e6855-137">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e6855-138">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e6855-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e6855-139">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e6855-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6855-140">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e6855-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a><span data-ttu-id="e6855-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6855-141">See Also</span></span>  
 [<span data-ttu-id="e6855-142">Beispiele für AppFabric-Management</span><span class="sxs-lookup"><span data-stu-id="e6855-142">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)
