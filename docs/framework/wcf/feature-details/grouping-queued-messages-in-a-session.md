---
title: Gruppieren von Nachrichten in der Warteschlange einer Sitzung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 9ad3bd29535e14231d07b9e491e606f8349ca3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290061"
---
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="412de-102">Gruppieren von Nachrichten in der Warteschlange einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="412de-102">Grouping Queued Messages in a Session</span></span>

<span data-ttu-id="412de-103">Windows Communication Foundation (WCF) stellt eine Sitzung bereit, mit der Sie einen Satz verwandter Nachrichten zur Verarbeitung durch eine einzelne empfangende Anwendung gruppieren können.</span><span class="sxs-lookup"><span data-stu-id="412de-103">Windows Communication Foundation (WCF) provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="412de-104">Die Nachrichten in einer Sitzung müssen Teil der gleichen Transaktion sein.</span><span class="sxs-lookup"><span data-stu-id="412de-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="412de-105">Da alle Nachrichten Teil der gleichen Transaktion sind, wird die gesamte Sitzung zurückgesetzt, wenn eine Nachricht nicht verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="412de-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="412de-106">Sitzungen weisen ähnliche Verhaltensweisen bezüglich Warteschlangen für unzustellbare Nachrichten und Warteschlangen für potenziell schädliche Nachrichten auf.</span><span class="sxs-lookup"><span data-stu-id="412de-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="412de-107">Die Time to Live (TTL)-Eigenschaft einer Bindung in der Warteschlange, die für Sitzungen konfiguriert wurde, wird auf die gesamte Sitzung angewendet.</span><span class="sxs-lookup"><span data-stu-id="412de-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="412de-108">Wenn nur ein Teil der Nachrichten in der Sitzung vor Ablauf der TTL gesendet wird, wird die gesamte Sitzung in der Warteschlange für unzustellbare Nachrichten abgelegt.</span><span class="sxs-lookup"><span data-stu-id="412de-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="412de-109">Analog wird ggf. die gesamte Sitzung in der Warteschlange für potenziell schädliche Nachrichten abgelegt, wenn Nachrichten in einer Sitzung nicht von der Anwendungswarteschlange an eine Anwendung gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="412de-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="412de-110">Beispiel für das Gruppieren von Nachrichten</span><span class="sxs-lookup"><span data-stu-id="412de-110">Message Grouping Example</span></span>  

 <span data-ttu-id="412de-111">Ein Beispiel für das Gruppieren von Nachrichten ist die Implementierung einer Anwendung zur Auftrags Verarbeitung als WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="412de-111">One example where grouping messages is helpful is when implementing an order-processing application as a WCF service.</span></span> <span data-ttu-id="412de-112">Angenommen, ein Client sendet einen Auftrag an diese Anwendung, die eine Anzahl von Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="412de-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="412de-113">Der Client ruft für jedes Element den Dienst auf. Dadurch wird jeweils eine separate Nachricht gesendet.</span><span class="sxs-lookup"><span data-stu-id="412de-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="412de-114">Es kann sein, dass Server A das erste Element empfängt und Server B das zweite.</span><span class="sxs-lookup"><span data-stu-id="412de-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="412de-115">Immer, wenn ein Element hinzugefügt wird, muss der Server, der das Element verarbeitet, die entsprechende Reihenfolge ermitteln, und das Element muss hinzugefügt werden. Dieser Vorgang ist nicht sehr effizient.</span><span class="sxs-lookup"><span data-stu-id="412de-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="412de-116">Dieses Problem tritt auch dann auf, wenn alle Anfragen nur von einem Server behandelt werden, da der Server alle Aufträge überwachen muss, die derzeit verarbeitet werden, und das neue Element einem Auftrag zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="412de-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="412de-117">Durch das Gruppieren aller Anforderungen für einen Auftrag wird die Implementierung einer solchen Anwendung stark vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="412de-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="412de-118">Alle Elemente für einen Auftrag werden von der Clientanwendung in einer Sitzung gesendet, sodass der Auftrag vom Dienst in einer Sitzung verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="412de-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="412de-119">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="412de-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="412de-120">So richten Sie einen Dienstvertrag für Sitzungen ein</span><span class="sxs-lookup"><span data-stu-id="412de-120">To set up a service contract to use sessions</span></span>  
  
1. <span data-ttu-id="412de-121">Definieren Sie einen Dienstvertrag, der eine Sitzung erfordert.</span><span class="sxs-lookup"><span data-stu-id="412de-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="412de-122">Verwenden Sie hierzu das-Attribut, indem Sie Folgendes <xref:System.ServiceModel.ServiceContractAttribute> angeben:</span><span class="sxs-lookup"><span data-stu-id="412de-122">Do this with the <xref:System.ServiceModel.ServiceContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. <span data-ttu-id="412de-123">Markieren Sie die Vorgänge im Vertrag als unidirektional, da von diesen Methoden nichts zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="412de-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="412de-124">Dies erfolgt mit dem- <xref:System.ServiceModel.OperationContractAttribute> Attribut, indem Folgendes angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="412de-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. <span data-ttu-id="412de-125">Implementieren Sie den Dienstvertrag, und geben Sie einen <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> von <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType> an.</span><span class="sxs-lookup"><span data-stu-id="412de-125">Implement the service contract and specify an <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span></span> <span data-ttu-id="412de-126">Dadurch wird der Dienst für jede Sitzung nur einmal instanziiert.</span><span class="sxs-lookup"><span data-stu-id="412de-126">This instantiates the service only once for each session.</span></span>  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. <span data-ttu-id="412de-127">Jeder Dienstvorgang erfordert eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="412de-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="412de-128">Verwenden Sie das <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut für die Angabe.</span><span class="sxs-lookup"><span data-stu-id="412de-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="412de-129">Der Vorgang, mit dem die Transaktion abgeschlossen wird, sollte auch <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="412de-129">The operation that completes the transaction should also set <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> to `true`.</span></span>  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    ```  
  
5. <span data-ttu-id="412de-130">Konfigurieren Sie einen Endpunkt, der die vom System bereitgestellte `NetMsmqBinding`-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="412de-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6. <span data-ttu-id="412de-131">Erstellen Sie eine Transaktionswarteschlange mit <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="412de-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="412de-132">Sie können die Warteschlange auch mit Message Queuing (MSMQ) oder MMC erstellen.</span><span class="sxs-lookup"><span data-stu-id="412de-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="412de-133">Erstellen Sie in diesem Fall eine Transaktionswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="412de-133">If you do, create a transactional queue.</span></span>  
  
7. <span data-ttu-id="412de-134">Erstellen Sie mit <xref:System.ServiceModel.ServiceHost> einen Host für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="412de-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8. <span data-ttu-id="412de-135">Öffnen Sie den Diensthost, um den Dienst verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="412de-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="412de-136">Schließen Sie den Diensthost.</span><span class="sxs-lookup"><span data-stu-id="412de-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="412de-137">So richten Sie einen Client ein</span><span class="sxs-lookup"><span data-stu-id="412de-137">To set up a client</span></span>  
  
1. <span data-ttu-id="412de-138">Erstellen Sie einen Transaktionsbereich zum Schreiben in die Transaktionswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="412de-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2. <span data-ttu-id="412de-139">Erstellen Sie den WCF-Client mit dem [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="412de-139">Create the WCF client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3. <span data-ttu-id="412de-140">Platzieren Sie den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="412de-140">Place the order.</span></span>  
  
4. <span data-ttu-id="412de-141">Schließen Sie den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="412de-141">Close the WCF client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="412de-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="412de-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="412de-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="412de-143">Description</span></span>  

 <span data-ttu-id="412de-144">Im folgenden Beispiel wird der Code für den `IProcessOrder`-Dienst sowie für einen Client bereitgestellt, der diesen Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="412de-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="412de-145">Es zeigt, wie WCF Warteschlangen Sitzungen verwendet, um das Gruppierungs Verhalten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="412de-145">It shows how WCF uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="412de-146">Code für den Dienst</span><span class="sxs-lookup"><span data-stu-id="412de-146">Code for the Service</span></span>  

 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a><span data-ttu-id="412de-147">Code für den Client</span><span class="sxs-lookup"><span data-stu-id="412de-147">Code for the Client</span></span>  

 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="412de-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="412de-148">See also</span></span>

- [<span data-ttu-id="412de-149">Sitzungen und Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="412de-149">Sessions and Queues</span></span>](../samples/sessions-and-queues.md)
- [<span data-ttu-id="412de-150">Warteschlangenübersicht</span><span class="sxs-lookup"><span data-stu-id="412de-150">Queues Overview</span></span>](queues-overview.md)
