---
title: 'Vorgehensweise: Erstellen eines Duplexvertrags'
description: Erfahren Sie, wie Sie einen Duplex Vertrag erstellen, der es WCF-Clients und-Servern ermöglicht, unabhängig voneinander zu kommunizieren. Beide können Aufrufe der anderen initiieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: cce1784865a1599e69c3f604c288ef62c9c43652
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243715"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="3c7a5-104">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="3c7a5-104">How to: Create a Duplex Contract</span></span>

<span data-ttu-id="3c7a5-105">Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen Duplexvertrag (bidirektionalen Vertrag) verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-105">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="3c7a5-106">Ein Duplexvertrag ermöglicht die unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils Anderen initiieren können.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-106">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="3c7a5-107">Der Duplex Vertrag ist eines von drei Nachrichten Mustern, die für Windows Communication Foundation (WCF)-Dienste verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-107">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="3c7a5-108">Die anderen beiden Nachrichtenmuster zeichnen sich durch unidirektionale Anforderungen bzw. Antworten aus.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-108">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="3c7a5-109">Ein Duplexvertrag besteht aus zwei unidirektionalen Verträgen zwischen Client und Server und erfordert nicht, dass die Methodenaufrufe korrelieren.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-109">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="3c7a5-110">Sie verwenden diese Art von Vertrag, wenn der Dienst vom Client weitere Informationen anfordern muss oder auf dem Client ausdrücklich Ereignisse auslösen muss.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-110">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="3c7a5-111">Weitere Informationen zum Erstellen einer Client Anwendung für einen Duplex Vertrag finden Sie unter Gewusst [wie: Zugreifen auf Dienste mit einem Duplex Vertrag](how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="3c7a5-111">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="3c7a5-112">Ein funktionierendes Beispiel finden Sie im [Duplex](../samples/duplex.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-112">For a working sample, see the [Duplex](../samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="3c7a5-113">So erstellen Sie einen Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="3c7a5-113">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="3c7a5-114">Erstellen Sie die Schnittstelle, die die Serverseite des Duplexvertrags bildet.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-114">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="3c7a5-115">Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-115">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="3c7a5-116">Deklarieren Sie die Methodensignaturen in der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-116">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="3c7a5-117">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-117">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="3c7a5-118">Erstellen Sie die Rückrufschnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-118">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="3c7a5-119">Deklarieren Sie die Methodesignaturen in der Rückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-119">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="3c7a5-120">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-120">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="3c7a5-121">Verknüpfen Sie die beiden Schnittstellen zu einem Duplexvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft der primären Schnittstelle auf den Typ der Rückrufschnittstelle festlegen.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-121">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="3c7a5-122">So rufen Sie Methoden auf dem Client auf</span><span class="sxs-lookup"><span data-stu-id="3c7a5-122">To call methods on the client</span></span>  
  
1. <span data-ttu-id="3c7a5-123">Deklarieren Sie in der Dienstimplementierung des primären Vertrags eine Variable für die Rückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-123">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="3c7a5-124">Legen Sie die Variable auf den von der <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A>-Methode der <xref:System.ServiceModel.OperationContext>-Klasse zurückgegebenen Objektverweis fest.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-124">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="3c7a5-125">Rufen Sie die in der Rückrufschnittstelle definierten Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-125">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c7a5-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c7a5-126">Example</span></span>  

 <span data-ttu-id="3c7a5-127">Der folgende Beispielcode veranschaulicht die Duplexkommunikation.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-127">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="3c7a5-128">Der Vertrag des Diensts enthält Dienstvorgänge zum vorwärts- und rückwärtsgerichteten Navigieren.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-128">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="3c7a5-129">Der Vertrag des Clients enthält einen Dienstvorgang zur Ausgabe seiner Position.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-129">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- <span data-ttu-id="3c7a5-130">Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in WSDL (Web Services Description Language) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-130">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
- <span data-ttu-id="3c7a5-131">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um das WSDL-Dokument und den (optionalen) Code und die Konfiguration für einen Client abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-131">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
- <span data-ttu-id="3c7a5-132">Endpunkte, die Duplexdienste verfügbar machen, müssen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-132">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="3c7a5-133">Wenn ein Dienst eine Duplexnachricht empfängt, überprüft er das ReplyTo-Element in dieser eingehenden Nachricht, um zu bestimmen, wohin die Antwort gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-133">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="3c7a5-134">Wenn der zum Empfangen der Nachricht verwendete Kanal nicht geschützt ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem ReplyTo-Element eines Zielcomputers senden, was auf diesem Zielcomputer zu einem Denial Of Service (DOS) führt.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-134">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="3c7a5-135">Bei gewöhnlichen Anforderung-Antwort-Nachrichten stellt dies kein Problem dar, weil das ReplyTo-Element ignoriert und die Antwort auf dem Kanal gesendet wird, auf dem die ursprüngliche Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3c7a5-135">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7a5-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c7a5-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="3c7a5-137">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="3c7a5-137">How to: Access Services with a Duplex Contract</span></span>](how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="3c7a5-138">Duplex</span><span class="sxs-lookup"><span data-stu-id="3c7a5-138">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="3c7a5-139">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="3c7a5-139">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="3c7a5-140">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="3c7a5-140">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="3c7a5-141">Sitzungskonsistenz</span><span class="sxs-lookup"><span data-stu-id="3c7a5-141">Session</span></span>](../samples/session.md)
