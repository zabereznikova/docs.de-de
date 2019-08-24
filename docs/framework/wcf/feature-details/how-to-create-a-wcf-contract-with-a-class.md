---
title: 'Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988750"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="8e7da-102">Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse</span><span class="sxs-lookup"><span data-stu-id="8e7da-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="8e7da-103">Die bevorzugte Methode zum Erstellen eines Windows Communication Foundation (WCF)-Vertrags ist die Verwendung einer-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8e7da-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="8e7da-104">Weitere Informationen finden Sie unter [Vorgehensweise: Definieren Sie einen Dienst](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)Vertrag.</span><span class="sxs-lookup"><span data-stu-id="8e7da-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="8e7da-105">Eine Alternative besteht darin, eine Klasse zu erstellen und anschließend das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt auf die Klasse anzuwenden und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die einzelnen Methoden in der Klasse, die Teil des Vertrags sind, anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="8e7da-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="8e7da-106">`[ServiceContract]` und `[ServiceContractAttribute]` dienen dem gleichen Zweck.</span><span class="sxs-lookup"><span data-stu-id="8e7da-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="8e7da-107">Dasselbe gilt für `[OperationContract]` und `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="8e7da-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="8e7da-108">In jedem Fall ist der erste Kurzwert für Letzteres.</span><span class="sxs-lookup"><span data-stu-id="8e7da-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="8e7da-109">Weitere Informationen zu Dienstverträgen finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="8e7da-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="8e7da-110">Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse</span><span class="sxs-lookup"><span data-stu-id="8e7da-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="8e7da-111">Erstellen Sie eine neue Klasse mit Visual Basic C#, oder einer beliebigen anderen Common Language Runtime Sprache.</span><span class="sxs-lookup"><span data-stu-id="8e7da-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="8e7da-112">Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="8e7da-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="8e7da-113">Erstellen Sie Methoden in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="8e7da-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="8e7da-114">Wenden Sie <xref:System.ServiceModel.OperationContractAttribute> die-Klasse auf jede Methode an, die als Teil des öffentlichen WCF-Vertrags verfügbar gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="8e7da-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e7da-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e7da-115">Example</span></span>  
 <span data-ttu-id="8e7da-116">Im folgenden Codebeispiel wird eine Klasse dargestellt, die einen Dienstvertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="8e7da-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="8e7da-117">Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster.</span><span class="sxs-lookup"><span data-stu-id="8e7da-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="8e7da-118">Weitere Informationen zu diesem Nachrichten Muster finden [Sie unter Gewusst wie: Erstellen Sie einen Anforderung-Antwort](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="8e7da-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="8e7da-119">Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen.</span><span class="sxs-lookup"><span data-stu-id="8e7da-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="8e7da-120">Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) Vertrags [und Gewusst wie: Erstellen Sie einen Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)Vertrag.</span><span class="sxs-lookup"><span data-stu-id="8e7da-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7da-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e7da-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
