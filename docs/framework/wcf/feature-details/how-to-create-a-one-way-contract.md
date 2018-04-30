---
title: 'Vorgehensweise: Erstellen eines unidirektionalen Vertrags'
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
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1a54b64826735d912bdf6507023da56118fb9a69
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-one-way-contract"></a><span data-ttu-id="2b4d2-102">Vorgehensweise: Erstellen eines unidirektionalen Vertrags</span><span class="sxs-lookup"><span data-stu-id="2b4d2-102">How to: Create a One-Way Contract</span></span>
<span data-ttu-id="2b4d2-103">Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen unidirektionalen Vertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-103">This topic shows the basic steps to create methods that use a one-way contract.</span></span> <span data-ttu-id="2b4d2-104">Solche Methoden rufen Vorgänge in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst von einem Client auf, erwarten aber keine Antwort.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-104">Such methods invoke operations on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service from a client but do not expect a reply.</span></span> <span data-ttu-id="2b4d2-105">Dieser Vertragstyp kann verwendet werden, um z.&#160;B. Benachrichtigungen für viele Abonnenten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-105">This type of contract can be used, for example, to publish notifications to many subscribers.</span></span> <span data-ttu-id="2b4d2-106">Sie können unidirektionale Verträge auch beim Erstellen eines Duplexvertrags (bidirektionalen Vertrags) verwenden. Dies ermöglicht eine unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils anderen initiieren können.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-106">You can also use one-way contracts when creating a duplex (two-way) contract, which allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="2b4d2-107">So wird insbesondere dem Server ermöglicht, unidirektionale Aufrufe an den Client durchzuführen, die der Client als Ereignisse behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-107">This can allow, in particular, the server to make one-way calls to the client that the client can treat as events.</span></span> <span data-ttu-id="2b4d2-108">Ausführliche Informationen zum Angeben von unidirektionalen Methoden finden Sie in der Beschreibung zur <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Methode und zur <xref:System.ServiceModel.OperationContractAttribute>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-108">For detailed information about specifying one-way methods, see the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property and the <xref:System.ServiceModel.OperationContractAttribute> class.</span></span>  
  
 <span data-ttu-id="2b4d2-109">Weitere Informationen zum Erstellen von einer Clientanwendung für einen Duplexvertrag, finden Sie unter [Vorgehensweise: Access Services mit unidirektionalen und Anforderung-Antwort-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="2b4d2-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with One-Way and Request-Reply Contracts](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).</span></span> <span data-ttu-id="2b4d2-110">Ein funktionierendes Beispiel finden Sie unter der [unidirektionale](../../../../docs/framework/wcf/samples/one-way.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-110">For a working sample, see the [One-Way](../../../../docs/framework/wcf/samples/one-way.md) sample.</span></span>  
  
### <a name="to-create-a-one-way-contract"></a><span data-ttu-id="2b4d2-111">So erstellen Sie einen unidirektionalen Vertrag</span><span class="sxs-lookup"><span data-stu-id="2b4d2-111">To create a one-way contract</span></span>  
  
1.  <span data-ttu-id="2b4d2-112">Erstellen Sie einen Dienstvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle anwenden, die die Methoden definiert, die der Dienst implementieren soll.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-112">Create the service contract by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface that defines the methods the service is to implement.</span></span>  
  
2.  <span data-ttu-id="2b4d2-113">Geben Sie an, welche Methoden in der Schnittstelle ein Client aufrufen kann, indem Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf die Methoden anwenden.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-113">Indicate which methods in the interface a client can invoked by applying the <xref:System.ServiceModel.OperationContractAttribute> class to them.</span></span>  
  
3.  <span data-ttu-id="2b4d2-114">Definieren Sie die Vorgänge, die keine unidirektionale Ausgabe (keinen Rückgabewert und keine out- oder ref-Parameter) haben dürfen, indem Sie die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-114">Designate operations that must have no output (no return value and no out or ref parameters) as one-way by setting the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true`.</span></span> <span data-ttu-id="2b4d2-115">Beachten Sie, dass alle Vorgänge mit der <xref:System.ServiceModel.OperationContractAttribute>-Klasse standardmäßig einen Anforderung-Antwort-Vertrag erfüllen, weil die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft standardmäßig `false` lautet.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-115">Note that the operations that carry the <xref:System.ServiceModel.OperationContractAttribute> class satisfy a request-reply contract by default because the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property is `false` by default.</span></span> <span data-ttu-id="2b4d2-116">Wenn Sie einen unidirektionalen Vertrag für die Methode definieren möchten, müssen Sie den Wert der Attributeigenschaft folglich explizit auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-116">So you must explicitly specify the value of the attribute property to be `true` if you want a one-way contract for the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b4d2-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b4d2-117">Example</span></span>  
 <span data-ttu-id="2b4d2-118">Im folgenden Codebeispiel wird ein Vertrag für einen Dienst definiert, der mehrere unidirektionale Methoden besitzt.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-118">The following code example defines a contract for a service that includes several one-way methods.</span></span> <span data-ttu-id="2b4d2-119">Alle diese Methoden haben unidirektionale Verträge mit Ausnahme von `Equals`, das standardmäßig auf Anforderung-Antwort festgelegt ist und ein Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-119">All of the methods have one-way contracts except `Equals`, which defaults to request-reply and returns a result.</span></span>  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2b4d2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b4d2-120">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="2b4d2-121">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="2b4d2-121">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="2b4d2-122">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="2b4d2-122">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="2b4d2-123">Sitzung</span><span class="sxs-lookup"><span data-stu-id="2b4d2-123">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)  
 [<span data-ttu-id="2b4d2-124">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="2b4d2-124">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
