---
title: 'Vorgehensweise: Erstellen eines Duplexvertrags'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: e5b6c7eecce08a23490b6ab1991e4561d9462469
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598982"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="850f7-102">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="850f7-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="850f7-103">Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen Duplexvertrag (bidirektionalen Vertrag) verwenden.</span><span class="sxs-lookup"><span data-stu-id="850f7-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="850f7-104">Ein Duplexvertrag ermöglicht die unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils Anderen initiieren können.</span><span class="sxs-lookup"><span data-stu-id="850f7-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="850f7-105">Der Duplex Vertrag ist eines von drei Nachrichten Mustern, die für Windows Communication Foundation (WCF)-Dienste verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="850f7-105">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="850f7-106">Die anderen beiden Nachrichtenmuster zeichnen sich durch unidirektionale Anforderungen bzw. Antworten aus.</span><span class="sxs-lookup"><span data-stu-id="850f7-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="850f7-107">Ein Duplexvertrag besteht aus zwei unidirektionalen Verträgen zwischen Client und Server und erfordert nicht, dass die Methodenaufrufe korrelieren.</span><span class="sxs-lookup"><span data-stu-id="850f7-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="850f7-108">Sie verwenden diese Art von Vertrag, wenn der Dienst vom Client weitere Informationen anfordern muss oder auf dem Client ausdrücklich Ereignisse auslösen muss.</span><span class="sxs-lookup"><span data-stu-id="850f7-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="850f7-109">Weitere Informationen zum Erstellen einer Client Anwendung für einen Duplex Vertrag finden Sie unter Gewusst [wie: Zugreifen auf Dienste mit einem Duplex Vertrag](how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="850f7-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="850f7-110">Ein funktionierendes Beispiel finden Sie im [Duplex](../samples/duplex.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="850f7-110">For a working sample, see the [Duplex](../samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="850f7-111">So erstellen Sie einen Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="850f7-111">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="850f7-112">Erstellen Sie die Schnittstelle, die die Serverseite des Duplexvertrags bildet.</span><span class="sxs-lookup"><span data-stu-id="850f7-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="850f7-113">Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="850f7-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="850f7-114">Deklarieren Sie die Methodensignaturen in der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="850f7-114">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="850f7-115">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.</span><span class="sxs-lookup"><span data-stu-id="850f7-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="850f7-116">Erstellen Sie die Rückrufschnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="850f7-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="850f7-117">Deklarieren Sie die Methodesignaturen in der Rückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="850f7-117">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="850f7-118">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.</span><span class="sxs-lookup"><span data-stu-id="850f7-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="850f7-119">Verknüpfen Sie die beiden Schnittstellen zu einem Duplexvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft der primären Schnittstelle auf den Typ der Rückrufschnittstelle festlegen.</span><span class="sxs-lookup"><span data-stu-id="850f7-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="850f7-120">So rufen Sie Methoden auf dem Client auf</span><span class="sxs-lookup"><span data-stu-id="850f7-120">To call methods on the client</span></span>  
  
1. <span data-ttu-id="850f7-121">Deklarieren Sie in der Dienstimplementierung des primären Vertrags eine Variable für die Rückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="850f7-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="850f7-122">Legen Sie die Variable auf den von der <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A>-Methode der <xref:System.ServiceModel.OperationContext>-Klasse zurückgegebenen Objektverweis fest.</span><span class="sxs-lookup"><span data-stu-id="850f7-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="850f7-123">Rufen Sie die in der Rückrufschnittstelle definierten Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="850f7-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="850f7-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="850f7-124">Example</span></span>  
 <span data-ttu-id="850f7-125">Der folgende Beispielcode veranschaulicht die Duplexkommunikation.</span><span class="sxs-lookup"><span data-stu-id="850f7-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="850f7-126">Der Vertrag des Diensts enthält Dienstvorgänge zum vorwärts- und rückwärtsgerichteten Navigieren.</span><span class="sxs-lookup"><span data-stu-id="850f7-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="850f7-127">Der Vertrag des Clients enthält einen Dienstvorgang zur Ausgabe seiner Position.</span><span class="sxs-lookup"><span data-stu-id="850f7-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- <span data-ttu-id="850f7-128">Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in WSDL (Web Services Description Language) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="850f7-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
- <span data-ttu-id="850f7-129">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um das WSDL-Dokument und den (optionalen) Code und die Konfiguration für einen Client abzurufen.</span><span class="sxs-lookup"><span data-stu-id="850f7-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
- <span data-ttu-id="850f7-130">Endpunkte, die Duplexdienste verfügbar machen, müssen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="850f7-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="850f7-131">Wenn ein Dienst eine Duplexnachricht empfängt, überprüft er das ReplyTo-Element in dieser eingehenden Nachricht, um zu bestimmen, wohin die Antwort gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="850f7-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="850f7-132">Wenn der zum Empfangen der Nachricht verwendete Kanal nicht geschützt ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem ReplyTo-Element eines Zielcomputers senden, was auf diesem Zielcomputer zu einem Denial Of Service (DOS) führt.</span><span class="sxs-lookup"><span data-stu-id="850f7-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="850f7-133">Bei gewöhnlichen Anforderung-Antwort-Nachrichten stellt dies kein Problem dar, weil das ReplyTo-Element ignoriert und die Antwort auf dem Kanal gesendet wird, auf dem die ursprüngliche Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="850f7-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850f7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="850f7-134">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="850f7-135">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="850f7-135">How to: Access Services with a Duplex Contract</span></span>](how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="850f7-136">Duplex</span><span class="sxs-lookup"><span data-stu-id="850f7-136">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="850f7-137">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="850f7-137">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="850f7-138">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="850f7-138">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="850f7-139">Sitzung</span><span class="sxs-lookup"><span data-stu-id="850f7-139">Session</span></span>](../samples/session.md)
