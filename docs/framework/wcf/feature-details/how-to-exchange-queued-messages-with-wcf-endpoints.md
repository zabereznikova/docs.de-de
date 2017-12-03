---
title: 'Gewusst wie: Austauschen von Nachrichten in einer Warteschlange mit WCD-Endpunkten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6c50d9c6740b0c680e349a71bf4b3bdece2b34f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="48c77-102">Gewusst wie: Austauschen von Nachrichten in einer Warteschlange mit WCD-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="48c77-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="48c77-103">Warteschlangen stellen sicher, dass ein zuverlässiger Nachrichtenaustausch zwischen einem Client und einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst stattfinden kann, selbst wenn der Dienst zum Zeitpunkt der Kommunikation nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="48c77-103">Queues ensure that reliable messaging can occur between a client and a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="48c77-104">Die folgenden Vorgänge zeigen, wie Sie eine stabile Kommunikation zwischen einem Client und einem Dienst sicherstellen können, indem Sie die Standardbindung in der Warteschlange beim Implementieren des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="48c77-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="48c77-105">Dieser Abschnitt erläutert die Verwendung der <xref:System.ServiceModel.NetMsmqBinding> für die Kommunikation in einer Warteschlange zwischen einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst.</span><span class="sxs-lookup"><span data-stu-id="48c77-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="48c77-106">So verwenden Sie Warteschlangen in einem WCD-Dienst</span><span class="sxs-lookup"><span data-stu-id="48c77-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="48c77-107">Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="48c77-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="48c77-108">Kennzeichnen Sie die Vorgänge in der Schnittstelle, die Teil des Dienstvertrags mit dem <xref:System.ServiceModel.OperationContractAttribute> sind, und legen Sie sie als einseitig fest, da keine Antwort an die Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="48c77-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="48c77-109">Im folgenden Codebeispiel wird ein Dienstvertrag mit seiner Vorgangsdefinition dargestellt.</span><span class="sxs-lookup"><span data-stu-id="48c77-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="48c77-110">Wenn der Dienstvertrag benutzerdefinierte Typen übergibt, müssen Sie Datenverträge für diese Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="48c77-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="48c77-111">Der folgende Code stellt zwei Datenverträge dar: `PurchaseOrder` und `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="48c77-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="48c77-112">Die beiden Typen definieren die Daten, die an den Dienst gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="48c77-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="48c77-113">(Beachten Sie, dass die Klassen, die diesen Datenvertrag definieren, auch verschiedene Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="48c77-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="48c77-114">Diese Methoden werden nicht als Teil des Datenvertrags behandelt.</span><span class="sxs-lookup"><span data-stu-id="48c77-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="48c77-115">Nur Member, die mit dem `DataMember`-Attribut deklariert werden, sind Teil des Datenvertrags.)</span><span class="sxs-lookup"><span data-stu-id="48c77-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="48c77-116">Implementieren Sie die Methoden des Dienstvertrags, die  in der Schnittstelle in einer Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="48c77-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="48c77-117">Beachten Sie, dass das <xref:System.ServiceModel.OperationBehaviorAttribute> für die `SubmitPurchaseOrder`-Methode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="48c77-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="48c77-118">Hiermit wird angegeben, dass der Vorgang in einer Transaktion aufgerufen werden muss und dass die Transaktion automatisch beendet wird, wenn die Methode beendet wird.</span><span class="sxs-lookup"><span data-stu-id="48c77-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="48c77-119">Erstellen Sie eine Transaktionswarteschlange mit <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="48c77-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="48c77-120">Sie können die Warteschlange stattdessen auch mit der Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="48c77-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="48c77-121">Erstellen Sie in diesem Fall unbedingt eine Transaktionswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="48c77-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="48c77-122">Definieren Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> in einer Konfiguration, der die Dienstadresse festlegt und die Standard-<xref:System.ServiceModel.NetMsmqBinding>-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="48c77-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="48c77-123">mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Konfiguration finden Sie unter [Konfigurieren von Windows Communication Foundation-Anwendungen](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="48c77-123"> using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="48c77-124">Erstellen Sie einen Host für den `OrderProcessing`-Dienst mit <xref:System.ServiceModel.ServiceHost>, der Nachrichten aus der Warteschlange liest und sie verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="48c77-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="48c77-125">Öffnen Sie den Diensthost, um den Dienst verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="48c77-125">Open the service host to make the service available.</span></span> <span data-ttu-id="48c77-126">Zeigen Sie eine Meldung an, die den Benutzer darüber informiert, dass er den Dienst durch Drücken einer beliebigen Taste beenden kann.</span><span class="sxs-lookup"><span data-stu-id="48c77-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="48c77-127">Rufen Sie `ReadLine` auf, damit auf das Drücken einer Taste gewartet und dann der Dienst geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="48c77-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="48c77-128">So erstellen Sie einen Client für einen Dienst in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="48c77-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="48c77-129">Das folgende Beispiel veranschaulicht, wie die Hostinganwendung ausgeführt und das Tool "Svcutil.exe" verwendet wird, um den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="48c77-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="48c77-130">Definieren Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> in einer Konfiguration, die die Adresse festlegt und die Standard-<xref:System.ServiceModel.NetMsmqBinding>-Bindung verwendet, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="48c77-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="48c77-131">Erstellen Sie einen Transaktionsbereich zum Schreiben in die Transaktionswarteschlange, rufen Sie den `SubmitPurchaseOrder`-Vorgang auf, und schließen Sie den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="48c77-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="48c77-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48c77-132">Example</span></span>  
 <span data-ttu-id="48c77-133">Die folgenden Beispiele veranschaulichen den Dienstcode, die Hostinganwendung, die App.config-Datei und den Clientcode, die für dieses Beispiel eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="48c77-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="48c77-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48c77-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="48c77-135">Abgewickelte MSMQ-Bindung</span><span class="sxs-lookup"><span data-stu-id="48c77-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="48c77-136">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="48c77-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="48c77-137">Vorgehensweise: Nachrichtenaustausch mit WCF-Endpunkten und Message Queuing-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="48c77-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="48c77-138">Windows Communication Foundation zu Message Queuing</span><span class="sxs-lookup"><span data-stu-id="48c77-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="48c77-139">Installieren von Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="48c77-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="48c77-140">Message Queuing-Integration Bindung-Beispiele</span><span class="sxs-lookup"><span data-stu-id="48c77-140">Message Queuing Integration Binding Samples</span></span>](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="48c77-141">Message Queuing zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="48c77-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="48c77-142">Nachrichtensicherheit über Message Queuing</span><span class="sxs-lookup"><span data-stu-id="48c77-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
