---
title: 'Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4af593edd355ed89da8c5b2c79a4c029b966fe4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="c1d98-102">Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1d98-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="c1d98-103">Die bevorzugte Möglichkeit, einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Vertrag zu erstellen, ist die Verwendung einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c1d98-103">The preferred way to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="c1d98-104">Dieser Vertrag gibt die Auflistung und Struktur von Nachrichten an, die erforderlich sind, um auf die Vorgänge zuzugreifen, die der Dienst anbietet.</span><span class="sxs-lookup"><span data-stu-id="c1d98-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="c1d98-105">Diese Schnittstelle definiert die Eingabe- und Ausgabetypen durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle und der <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf die Methoden, die verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c1d98-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="c1d98-106">Weitere Informationen zu Dienstverträge, finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="c1d98-106">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="c1d98-107">Erstellen eines WCF-Vertrags mit einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1d98-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="c1d98-108">Erstellen Sie eine neue Schnittstelle, die mit Visual Basic, c# oder einer beliebigen anderen common Language Runtime-Sprache.</span><span class="sxs-lookup"><span data-stu-id="c1d98-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="c1d98-109">Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="c1d98-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="c1d98-110">Definieren Sie die Methoden in der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c1d98-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="c1d98-111">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methode an, die als Teil des öffentlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Vertrags verfügbar gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="c1d98-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1d98-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1d98-112">Example</span></span>  
 <span data-ttu-id="c1d98-113">Im folgenden Codebeispiel wird eine Schnittstelle dargestellt, die einen Dienstvertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="c1d98-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="c1d98-114">Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster.</span><span class="sxs-lookup"><span data-stu-id="c1d98-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="c1d98-115">Weitere Informationen zu diesem Nachrichtenmuster finden Sie unter [Vorgehensweise: Erstellen Sie einen Anforderung-Antwort-Vertrag](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c1d98-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="c1d98-116">Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen.</span><span class="sxs-lookup"><span data-stu-id="c1d98-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="c1d98-117">Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) und [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c1d98-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d98-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1d98-118">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
