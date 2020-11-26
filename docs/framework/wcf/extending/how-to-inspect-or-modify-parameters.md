---
title: 'Vorgehensweise: Überprüfen oder Ändern von Parametern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: e8b2674d8efc0ef3ac2f1dd6ab0df559195c274c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249032"
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="434ea-102">Vorgehensweise: Überprüfen oder Ändern von Parametern</span><span class="sxs-lookup"><span data-stu-id="434ea-102">How to: Inspect or Modify Parameters</span></span>

<span data-ttu-id="434ea-103">Sie können die eingehenden oder ausgehenden Nachrichten für einen einzelnen Vorgang für ein Windows Communication Foundation (WCF)-Client Objekt oder einen WCF-Dienst überprüfen oder ändern, indem Sie die <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> -Schnittstelle implementieren und in den Client oder die Dienst Laufzeit einfügen.</span><span class="sxs-lookup"><span data-stu-id="434ea-103">You can inspect or modify the incoming or outgoing messages for a single operation on a Windows Communication Foundation (WCF) client object or a WCF service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="434ea-104">In der Regel wird ein Vorgangsverhalten verwendet, um Parameterinspektoren für einen einzelnen Vorgang hinzufügen; weitere Verhalten können für einen einfachen Zugriff auf die Laufzeit in größerem Umfang verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="434ea-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="434ea-105">Weitere Informationen finden Sie unter [Erweitern von Clients](extending-clients.md) und [erweitern](extending-dispatchers.md)von Verteilern.</span><span class="sxs-lookup"><span data-stu-id="434ea-105">For more information, see [Extending Clients](extending-clients.md) and [Extending Dispatchers](extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="434ea-106">Überprüfen oder Ändern von Parametern</span><span class="sxs-lookup"><span data-stu-id="434ea-106">Inspecting or Modifying Parameters</span></span>  
  
1. <span data-ttu-id="434ea-107">Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="434ea-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="434ea-108">Implementieren Sie <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (je nach erforderlichem Bereich), um den Eigenschaften <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> den Parameterinspektor hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="434ea-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3. <span data-ttu-id="434ea-109">Fügen Sie das Verhalten vor dem Aufrufen der <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>- oder <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode für  <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> ein.</span><span class="sxs-lookup"><span data-stu-id="434ea-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="434ea-110">Weitere Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="434ea-110">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="434ea-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="434ea-111">Example</span></span>  

 <span data-ttu-id="434ea-112">Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:</span><span class="sxs-lookup"><span data-stu-id="434ea-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="434ea-113">Eine Parameterinspektorimplementierung</span><span class="sxs-lookup"><span data-stu-id="434ea-113">A parameter inspector implementation.</span></span>  
  
- <span data-ttu-id="434ea-114">Die Verhaltensimplementierung, die den Parameterinspektor mit <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> und <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> einfügt.</span><span class="sxs-lookup"><span data-stu-id="434ea-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="434ea-115">Eine Konfigurationsdatei, die das Endpunktverhalten in eine Clientanwendung lädt und ausführt, um den Parameterinspektor für den Client einzufügen.</span><span class="sxs-lookup"><span data-stu-id="434ea-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="434ea-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="434ea-116">See also</span></span>

- [<span data-ttu-id="434ea-117">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="434ea-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)
