---
title: Client-Kanalebenenprogrammierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: cf6ee310e034ad7b2e53206e1bdba68007b1a268
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275579"
---
# <a name="client-channel-level-programming"></a><span data-ttu-id="6d33a-102">Client-Kanalebenenprogrammierung</span><span class="sxs-lookup"><span data-stu-id="6d33a-102">Client Channel-Level Programming</span></span>

<span data-ttu-id="6d33a-103">In diesem Thema wird beschrieben, wie Sie eine Windows Communication Foundation (WCF)-Client Anwendung schreiben, ohne die <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> -Klasse und das zugehörige-Objektmodell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d33a-103">This topic describes how to write a Windows Communication Foundation (WCF) client application without using the <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> class and its associated object model.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="6d33a-104">Senden von Nachrichten</span><span class="sxs-lookup"><span data-stu-id="6d33a-104">Sending Messages</span></span>  

 <span data-ttu-id="6d33a-105">Um für das Senden von Nachrichten und das Empfangen und Verarbeiten von Antworten bereit zu sein, sind die folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6d33a-105">To be ready to send messages and receive and process replies, the following steps are required:</span></span>  
  
1. <span data-ttu-id="6d33a-106">Erstellen Sie eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="6d33a-106">Create a binding.</span></span>  
  
2. <span data-ttu-id="6d33a-107">Erstellen einer Kanalfactory.</span><span class="sxs-lookup"><span data-stu-id="6d33a-107">Build a channel factory.</span></span>  
  
3. <span data-ttu-id="6d33a-108">Erstellen eines Kanals</span><span class="sxs-lookup"><span data-stu-id="6d33a-108">Create a channel.</span></span>  
  
4. <span data-ttu-id="6d33a-109">Senden einer Anforderung und Lesen der Antwort.</span><span class="sxs-lookup"><span data-stu-id="6d33a-109">Send a request and read the reply.</span></span>  
  
5. <span data-ttu-id="6d33a-110">Schließen Sie alle Kanalobjekte.</span><span class="sxs-lookup"><span data-stu-id="6d33a-110">Close all channel objects.</span></span>  
  
#### <a name="creating-a-binding"></a><span data-ttu-id="6d33a-111">Erstellen einer Bindung</span><span class="sxs-lookup"><span data-stu-id="6d33a-111">Creating a Binding</span></span>  

 <span data-ttu-id="6d33a-112">Vergleichbar mit dem empfangenden Fall (siehe [Service Channel-Level Programming](service-channel-level-programming.md)), wird das Senden von Nachrichten gestartet, indem eine Bindung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6d33a-112">Similar to the receiving case (see [Service Channel-Level Programming](service-channel-level-programming.md)), sending messages starts by creating a binding.</span></span> <span data-ttu-id="6d33a-113">In diesem Beispiel wird eine neue <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> erstellt und ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> seiner Elementauflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d33a-113">This example creates a new <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> and adds an <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> to its Elements collection.</span></span>  
  
#### <a name="building-a-channelfactory"></a><span data-ttu-id="6d33a-114">Erstellen einer ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="6d33a-114">Building a ChannelFactory</span></span>  

 <span data-ttu-id="6d33a-115">Anstatt einen <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType> zu erstellen, wird hier eine <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> erstellt, indem <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> auf der Bindung aufgerufen wird, bei der der Typparameter <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="6d33a-115">Instead of creating a <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, this time we create a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> by calling <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> on the binding where the type parameter is <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6d33a-116">Während die Kanallistener von der Seite verwendet werden, die auf eingehende Nachrichten wartet, werden Kanalfactorys von der Seite verwendet, die die Kommunikation für die Erstellung eines Kanals initiiert.</span><span class="sxs-lookup"><span data-stu-id="6d33a-116">While channel listeners are used by the side that waits for incoming messages, channel factories are used by the side that initiates the communication to create a channel.</span></span> <span data-ttu-id="6d33a-117">Wie Kanallistener müssen auch Kanalfactorys zuerst geöffnet werden, bevor sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6d33a-117">Just like channel listeners, channel factories must be opened first before they can be used.</span></span>  
  
#### <a name="creating-a-channel"></a><span data-ttu-id="6d33a-118">Erstellen eines Kanals</span><span class="sxs-lookup"><span data-stu-id="6d33a-118">Creating a Channel</span></span>  

 <span data-ttu-id="6d33a-119">Wir rufen dann <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> auf, um einen <xref:System.ServiceModel.Channels.IRequestChannel> zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d33a-119">We then call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> to create an <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span> <span data-ttu-id="6d33a-120">Dieser Aufruf nimmt die Adresse des Endpunkts, mit dem wir mithilfe des neu erstellten Kanals kommunizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6d33a-120">This call takes the address of the endpoint with which we want to communicate using the new channel being created.</span></span> <span data-ttu-id="6d33a-121">Nachdem wir einen Kanal haben, führen wir einen Öffnen-Vorgang an diesem durch, um ihn in einen Bereitschaftsstatus für die Kommunikation zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="6d33a-121">Once we have a channel, we call Open on it to put it in a state ready for communication.</span></span> <span data-ttu-id="6d33a-122">Abhängig von der Natur des Transports initiiert dieser Aufruf zum Öffnen möglicherweise eine Verbindung mit dem Zielendpunkt, oder es geschieht nichts auf dem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="6d33a-122">Depending on the nature of the transport, this call to Open may initiate a connection with the target endpoint or may do nothing at all on the network.</span></span>  
  
#### <a name="sending-a-request-and-reading-the-reply"></a><span data-ttu-id="6d33a-123">Senden einer Anforderung und Lesen der Antwort</span><span class="sxs-lookup"><span data-stu-id="6d33a-123">Sending a Request and Reading the Reply</span></span>  

 <span data-ttu-id="6d33a-124">Nachdem wir einen offenen Kanal erhalten haben, können wir eine Nachricht erstellen und die Anforderungsmethode des Kanals nutzen, um die Anforderung zu senden und dann auf die Zustellung der Antwort zu warten.</span><span class="sxs-lookup"><span data-stu-id="6d33a-124">Once we have an opened channel, we can create a message and use the channel’s Request method to send the request and wait for the reply to come back.</span></span> <span data-ttu-id="6d33a-125">Wird diese Methode zurückgegeben, verfügen wir über eine Antwortnachricht, die wir lesen können, um die Antwort des Endpunkts herauszufinden.</span><span class="sxs-lookup"><span data-stu-id="6d33a-125">When this method returns, we have a reply message that we can read to find out what the endpoint’s reply was.</span></span>  
  
#### <a name="closing-objects"></a><span data-ttu-id="6d33a-126">Schließen von Objekten</span><span class="sxs-lookup"><span data-stu-id="6d33a-126">Closing Objects</span></span>  

 <span data-ttu-id="6d33a-127">Um Ressourcenverluste zu vermeiden, schließen wir in Kommunikationsvorgängen verwendete Objekte, wenn sie nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d33a-127">To avoid leaking resources, we close objects used in communications when they are no longer required.</span></span>  
  
 <span data-ttu-id="6d33a-128">Das folgende Codebeispiel zeigt einen grundlegenden Client, der die Kanalfactory zum Senden einer Nachricht und zum Lesen der Antwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d33a-128">The following code example shows a basic client using the channel factory to send a message and read the reply.</span></span>  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
