---
title: 'Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: c7d4bce174790b97db6b95aa5d15af455f261f82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597162"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="5acd4-102">Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="5acd4-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="5acd4-103">Die bevorzugte Methode zum Erstellen eines Windows Communication Foundation (WCF)-Vertrags ist die Verwendung einer-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5acd4-103">The preferred way to create a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="5acd4-104">Dieser Vertrag gibt die Auflistung und Struktur von Nachrichten an, die erforderlich sind, um auf die Vorgänge zuzugreifen, die der Dienst anbietet.</span><span class="sxs-lookup"><span data-stu-id="5acd4-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="5acd4-105">Diese Schnittstelle definiert die Eingabe- und Ausgabetypen durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle und der <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf die Methoden, die verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5acd4-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="5acd4-106">Weitere Informationen zu Dienstverträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="5acd4-106">For more information about service contracts, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="5acd4-107">Erstellen eines WCF-Vertrags mit einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5acd4-107">Creating a WCF contract with an interface</span></span>  
  
1. <span data-ttu-id="5acd4-108">Erstellen Sie mit Visual Basic, c# oder einer beliebigen anderen Common Language Runtime Sprache eine neue Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5acd4-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="5acd4-109">Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="5acd4-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3. <span data-ttu-id="5acd4-110">Definieren Sie die Methoden in der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5acd4-110">Define the methods in the interface.</span></span>  
  
4. <span data-ttu-id="5acd4-111">Wenden Sie die- <xref:System.ServiceModel.OperationContractAttribute> Klasse auf jede Methode an, die als Teil des öffentlichen WCF-Vertrags verfügbar gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="5acd4-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5acd4-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5acd4-112">Example</span></span>  
 <span data-ttu-id="5acd4-113">Im folgenden Codebeispiel wird eine Schnittstelle dargestellt, die einen Dienstvertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="5acd4-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="5acd4-114">Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster.</span><span class="sxs-lookup"><span data-stu-id="5acd4-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="5acd4-115">Weitere Informationen zu diesem Nachrichten Muster finden Sie unter Gewusst [wie: Erstellen eines Anforderung-Antwort-Vertrags](how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="5acd4-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="5acd4-116">Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen.</span><span class="sxs-lookup"><span data-stu-id="5acd4-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="5acd4-117">Weitere Beispiele finden Sie unter Gewusst [wie: Erstellen](how-to-create-a-one-way-contract.md) eines unidirektionalen Vertrags und Gewusst [wie: Erstellen eines Duplex Vertrags](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="5acd4-117">For more examples, see [How to: Create a One-Way Contract](how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5acd4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5acd4-118">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
