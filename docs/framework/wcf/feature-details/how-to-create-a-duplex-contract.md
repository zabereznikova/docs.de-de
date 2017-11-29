---
title: 'Vorgehensweise: Erstellen eines Duplexvertrags'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 537e86b4eb43864e9a27d5a8a485ea5cb752833d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="9f1d9-102">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="9f1d9-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="9f1d9-103">Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen Duplexvertrag (bidirektionalen Vertrag) verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="9f1d9-104">Ein Duplexvertrag ermöglicht die unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils Anderen initiieren können.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="9f1d9-105">Der Duplexvertrag ist eines der drei Nachrichtenmuster, die für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-105">The duplex contract is one of three message patterns available to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="9f1d9-106">Die anderen beiden Nachrichtenmuster zeichnen sich durch unidirektionale Anforderungen bzw. Antworten aus.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="9f1d9-107">Ein Duplexvertrag besteht aus zwei unidirektionalen Verträgen zwischen Client und Server und erfordert nicht, dass die Methodenaufrufe korrelieren.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="9f1d9-108">Sie verwenden diese Art von Vertrag, wenn der Dienst vom Client weitere Informationen anfordern muss oder auf dem Client ausdrücklich Ereignisse auslösen muss.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f1d9-109">Erstellen eine Clientanwendung für einen Duplexvertrag finden Sie unter [Vorgehensweise: Access Services mit einem Duplexvertrag](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="9f1d9-109"> creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="9f1d9-110">Ein funktionierendes Beispiel finden Sie unter der [Duplex](../../../../docs/framework/wcf/samples/duplex.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-110">For a working sample, see the [Duplex](../../../../docs/framework/wcf/samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="9f1d9-111">So erstellen Sie einen Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="9f1d9-111">To create a duplex contract</span></span>  
  
1.  <span data-ttu-id="9f1d9-112">Erstellen Sie die Schnittstelle, die die Serverseite des Duplexvertrags bildet.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2.  <span data-ttu-id="9f1d9-113">Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3.  <span data-ttu-id="9f1d9-114">Deklarieren Sie die Methodensignaturen in der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-114">Declare the method signatures in the interface.</span></span>  
  
4.  <span data-ttu-id="9f1d9-115">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5.  <span data-ttu-id="9f1d9-116">Erstellen Sie die Rückrufschnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6.  <span data-ttu-id="9f1d9-117">Deklarieren Sie die Methodesignaturen in der Rückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-117">Declare the method signatures in the callback interface.</span></span>  
  
7.  <span data-ttu-id="9f1d9-118">Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8.  <span data-ttu-id="9f1d9-119">Verknüpfen Sie die beiden Schnittstellen zu einem Duplexvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft der primären Schnittstelle auf den Typ der Rückrufschnittstelle festlegen.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="9f1d9-120">So rufen Sie Methoden auf dem Client auf</span><span class="sxs-lookup"><span data-stu-id="9f1d9-120">To call methods on the client</span></span>  
  
1.  <span data-ttu-id="9f1d9-121">Deklarieren Sie in der Dienstimplementierung des primären Vertrags eine Variable für die Rückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2.  <span data-ttu-id="9f1d9-122">Legen Sie die Variable auf den von der <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A>-Methode der <xref:System.ServiceModel.OperationContext>-Klasse zurückgegebenen Objektverweis fest.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3.  <span data-ttu-id="9f1d9-123">Rufen Sie die in der Rückrufschnittstelle definierten Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f1d9-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f1d9-124">Example</span></span>  
 <span data-ttu-id="9f1d9-125">Der folgende Beispielcode veranschaulicht die Duplexkommunikation.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="9f1d9-126">Der Vertrag des Diensts enthält Dienstvorgänge zum vorwärts- und rückwärtsgerichteten Navigieren.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="9f1d9-127">Der Vertrag des Clients enthält einen Dienstvorgang zur Ausgabe seiner Position.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   <span data-ttu-id="9f1d9-128">Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in WSDL (Web Services Description Language) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
-   <span data-ttu-id="9f1d9-129">Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Abrufen des WSDL-Dokument und (optional) Code und Konfiguration für einen Client.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
-   <span data-ttu-id="9f1d9-130">Endpunkte, die Duplexdienste verfügbar machen, müssen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="9f1d9-131">Wenn ein Dienst eine Duplexnachricht empfängt, überprüft er das ReplyTo-Element in dieser eingehenden Nachricht, um zu bestimmen, wohin die Antwort gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="9f1d9-132">Wenn der zum Empfangen der Nachricht verwendete Kanal nicht geschützt ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem ReplyTo-Element eines Zielcomputers senden, was auf diesem Zielcomputer zu einem Denial Of Service (DOS) führt.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="9f1d9-133">Bei gewöhnlichen Anforderung-Antwort-Nachrichten stellt dies kein Problem dar, weil das ReplyTo-Element ignoriert und die Antwort auf dem Kanal gesendet wird, auf dem die ursprüngliche Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f1d9-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1d9-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f1d9-134">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="9f1d9-135">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="9f1d9-135">How to: Access Services with a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="9f1d9-136">Duplex</span><span class="sxs-lookup"><span data-stu-id="9f1d9-136">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)  
 [<span data-ttu-id="9f1d9-137">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="9f1d9-137">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="9f1d9-138">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="9f1d9-138">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="9f1d9-139">Sitzung</span><span class="sxs-lookup"><span data-stu-id="9f1d9-139">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)
