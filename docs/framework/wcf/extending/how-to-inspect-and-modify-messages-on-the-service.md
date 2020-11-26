---
title: 'Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 8d1ce6ef00462adb38e3d59c3d9bd35694c4dbe9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249058"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="5dde0-102">Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst</span><span class="sxs-lookup"><span data-stu-id="5dde0-102">How to: Inspect and Modify Messages on the Service</span></span>

<span data-ttu-id="5dde0-103">Sie können die eingehenden oder ausgehenden Nachrichten über einen Windows Communication Foundation (WCF)-Client überprüfen oder ändern, indem Sie einen implementieren <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> und ihn in die Dienst Laufzeit einfügen.</span><span class="sxs-lookup"><span data-stu-id="5dde0-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="5dde0-104">Weitere Informationen finden Sie unter [Erweitern von Dispatchern](extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="5dde0-104">For more information, see [Extending Dispatchers](extending-dispatchers.md).</span></span> <span data-ttu-id="5dde0-105">Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5dde0-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="5dde0-106">So überprüfen oder ändern Sie Nachrichten</span><span class="sxs-lookup"><span data-stu-id="5dde0-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="5dde0-107">Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5dde0-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="5dde0-108">Implementieren Sie eine <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>-, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>- oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>-Schnittstelle, je nach dem Umfang, in dem Sie Ihren Dienstnachrichteninspektor auf einfache Weise einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="5dde0-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="5dde0-109">Fügen Sie Ihr Verhalten ein, bevor Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode auf dem <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5dde0-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5dde0-110">Weitere Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="5dde0-110">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dde0-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dde0-111">Example</span></span>  

 <span data-ttu-id="5dde0-112">Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5dde0-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="5dde0-113">Eine Dienstinspektorimplementierung.</span><span class="sxs-lookup"><span data-stu-id="5dde0-113">A service inspector implementation.</span></span>  
  
- <span data-ttu-id="5dde0-114">Ein Dienstverhalten, das den Inspektor einfügt.</span><span class="sxs-lookup"><span data-stu-id="5dde0-114">A service behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="5dde0-115">Eine Konfigurationsdatei, die das Verhalten lädt und in einer Dienstanwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="5dde0-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="5dde0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dde0-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="5dde0-117">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="5dde0-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)
