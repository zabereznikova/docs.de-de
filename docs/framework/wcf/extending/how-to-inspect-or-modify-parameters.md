---
title: 'Vorgehensweise: Überprüfen oder Ändern von Parametern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: 329e25b31deb1761d8522636675fe3160cad9e15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721203"
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="40ee5-102">Vorgehensweise: Überprüfen oder Ändern von Parametern</span><span class="sxs-lookup"><span data-stu-id="40ee5-102">How to: Inspect or Modify Parameters</span></span>
<span data-ttu-id="40ee5-103">Sie können überprüfen, oder ändern Sie die eingehenden oder ausgehenden Nachrichten für einen einzelnen Vorgang auf einem Windows Communication Foundation (WCF)-Objekt oder einen WCF-Dienst durch die Implementierung der <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> -Schnittstelle und in den Client- oder Dienstlaufzeit einfügen.</span><span class="sxs-lookup"><span data-stu-id="40ee5-103">You can inspect or modify the incoming or outgoing messages for a single operation on a Windows Communication Foundation (WCF) client object or a WCF service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="40ee5-104">In der Regel wird ein Vorgangsverhalten verwendet, um Parameterinspektoren für einen einzelnen Vorgang hinzufügen; weitere Verhalten können für einen einfachen Zugriff auf die Laufzeit in größerem Umfang verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40ee5-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="40ee5-105">Weitere Informationen finden Sie unter [Erweitern von Clients](../../../../docs/framework/wcf/extending/extending-clients.md) und [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="40ee5-105">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md) and [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="40ee5-106">Überprüfen oder Ändern von Parametern</span><span class="sxs-lookup"><span data-stu-id="40ee5-106">Inspecting or Modifying Parameters</span></span>  
  
1.  <span data-ttu-id="40ee5-107">Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="40ee5-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="40ee5-108">Implementieren Sie <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (je nach erforderlichem Bereich), um den Eigenschaften <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> den Parameterinspektor hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="40ee5-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3.  <span data-ttu-id="40ee5-109">Fügen Sie das Verhalten vor dem Aufrufen der <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>- oder <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode für  <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> ein.</span><span class="sxs-lookup"><span data-stu-id="40ee5-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="40ee5-110">Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="40ee5-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40ee5-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40ee5-111">Example</span></span>  
 <span data-ttu-id="40ee5-112">Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:</span><span class="sxs-lookup"><span data-stu-id="40ee5-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="40ee5-113">Eine Parameterinspektorimplementierung</span><span class="sxs-lookup"><span data-stu-id="40ee5-113">A parameter inspector implementation.</span></span>  
  
-   <span data-ttu-id="40ee5-114">Die Verhaltensimplementierung, die den Parameterinspektor mit <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> und <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> einfügt.</span><span class="sxs-lookup"><span data-stu-id="40ee5-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="40ee5-115">Eine Konfigurationsdatei, die das Endpunktverhalten in eine Clientanwendung lädt und ausführt, um den Parameterinspektor für den Client einzufügen.</span><span class="sxs-lookup"><span data-stu-id="40ee5-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="40ee5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40ee5-116">See also</span></span>
- [<span data-ttu-id="40ee5-117">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="40ee5-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
