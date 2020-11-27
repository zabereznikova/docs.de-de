---
title: Verwenden von Verträgen im Workflow
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: e32130395e05a56de081620f82e0e6f72ae0db38
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289619"
---
# <a name="using-contracts-in-workflow"></a><span data-ttu-id="81cff-102">Verwenden von Verträgen im Workflow</span><span class="sxs-lookup"><span data-stu-id="81cff-102">Using Contracts in Workflow</span></span>

<span data-ttu-id="81cff-103">Beim Implementieren eines Diensts definieren Sie eine Reihe von Verträgen, in denen der Dienst und die von ihm gesendeten und empfangenen Daten beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="81cff-103">When implementing a service, you define a number of contracts that describe the service and the data that it sends and receives.</span></span> <span data-ttu-id="81cff-104">Die Daten werden als Datenverträge und Nachrichten Verträge dargestellt. sowohl WCF-als auch Workflow Dienste verwenden Daten Vertrags-und Nachrichten Vertrags Definitionen als Teil der Dienst Beschreibungen.</span><span class="sxs-lookup"><span data-stu-id="81cff-104">The data is represented as data contracts and message contracts; both WCF and workflow services use data contract and message contract definitions as part of service descriptions.</span></span> <span data-ttu-id="81cff-105">Der Dienst selbst macht Metadaten (im WSDL-Format) verfügbar, um die Vorgänge des Diensts zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="81cff-105">The service itself exposes metadata (in the form of WSDL) in order to describe the operations of the service.</span></span> <span data-ttu-id="81cff-106">Bei WCF definieren Dienst- und Vorgangsverträge den Dienst und seine unterstützten Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="81cff-106">In WCF, service contracts and operation contracts define the service and the operations it supports.</span></span> <span data-ttu-id="81cff-107">In einem Workflowdienst sind diese Verträge jedoch Teil des eigentlichen Geschäftsprozesses. Sie werden in den Metadaten von einem Prozess verfügbar gemacht, der als Vertragsrückschluss bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="81cff-107">However, in a workflow service, these contracts are part of the business process itself; they are exposed in metadata by a process called contract inference.</span></span>  
  
## <a name="contract-inference"></a><span data-ttu-id="81cff-108">Vertragsrückschluss</span><span class="sxs-lookup"><span data-stu-id="81cff-108">Contract Inference</span></span>  

 <span data-ttu-id="81cff-109">Wenn ein Workflowdienst mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, wird die Workflowdefinition untersucht, und basierend auf den im Workflow gefundenen Messagingaktivitäten wird ein Vertrag generiert.</span><span class="sxs-lookup"><span data-stu-id="81cff-109">When a workflow service is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, the workflow definition is examined and a contract is generated based on the set of messaging activities found in the workflow.</span></span> <span data-ttu-id="81cff-110">Zum Generieren des Vertrags werden insbesondere die folgenden Aktivitäten und Eigenschaften verwendet:</span><span class="sxs-lookup"><span data-stu-id="81cff-110">In particular the following activities and properties are used to generate the contract:</span></span>  
  
 <span data-ttu-id="81cff-111"><xref:System.ServiceModel.Activities.Receive> -Aktivität</span><span class="sxs-lookup"><span data-stu-id="81cff-111"><xref:System.ServiceModel.Activities.Receive> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>

 <span data-ttu-id="81cff-112"><xref:System.ServiceModel.Activities.SendReply> -Aktivität</span><span class="sxs-lookup"><span data-stu-id="81cff-112"><xref:System.ServiceModel.Activities.SendReply> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <span data-ttu-id="81cff-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> -Aktivität</span><span class="sxs-lookup"><span data-stu-id="81cff-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Activity</span></span>  
  
 <span data-ttu-id="81cff-114">Das Endergebnis des Vertragsrückschlusses ist eine Beschreibung des Diensts, bei der die gleichen Datenstrukturen wie für WCF-Dienstverträge und -Vorgangsverträge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81cff-114">The end result of contract inference is a description of the service using the same data structures as WCF service and operation contracts.</span></span> <span data-ttu-id="81cff-115">Diese Informationen werden dann verwendet, um WSDL für den Workflowdienst verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="81cff-115">This information is then used to expose WSDL for the workflow service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cff-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81cff-116">See also</span></span>

- [<span data-ttu-id="81cff-117">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="81cff-117">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="81cff-118">Messagingaktivitäten</span><span class="sxs-lookup"><span data-stu-id="81cff-118">Messaging Activities</span></span>](messaging-activities.md)
- [<span data-ttu-id="81cff-119">Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten</span><span class="sxs-lookup"><span data-stu-id="81cff-119">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)
- [<span data-ttu-id="81cff-120">Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="81cff-120">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
