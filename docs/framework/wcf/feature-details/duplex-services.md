---
title: Duplexdienste
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: f9e563cb87ee376e33442cdf718f70202d300f40
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895171"
---
# <a name="duplex-services"></a><span data-ttu-id="a2fde-102">Duplexdienste</span><span class="sxs-lookup"><span data-stu-id="a2fde-102">Duplex Services</span></span>

<span data-ttu-id="a2fde-103">Bei einem Duplexdienstvertrag handelt es sich um ein Nachrichtenaustauschmuster, bei dem beide Endpunkte eigenständig Nachrichten an den jeweils anderen Endpunkt senden können.</span><span class="sxs-lookup"><span data-stu-id="a2fde-103">A duplex service contract is a message exchange pattern in which both endpoints can send messages to the other independently.</span></span> <span data-ttu-id="a2fde-104">Daher kann ein Duplexdienst Nachrichten zurück an den Clientendpunkt senden und so ein ereignisähnliches Verhalten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-104">A duplex service, therefore, can send messages back to the client endpoint, providing event-like behavior.</span></span> <span data-ttu-id="a2fde-105">Eine Duplexkommunikation findet statt, wenn ein Client eine Verbindung mit einem Dienst herstellt und dem Dienst einen Kanal bereitstellt, über den dieser Nachrichten zurück an den Client senden kann.</span><span class="sxs-lookup"><span data-stu-id="a2fde-105">Duplex communication occurs when a client connects to a service and provides the service with a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="a2fde-106">Beachten Sie, dass Duplexdienste nur innerhalb einer Sitzung ein ereignisähnliches Verhalten zeigen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-106">Note that the event-like behavior of duplex services only works within a session.</span></span>

<span data-ttu-id="a2fde-107">Um einen Duplexvertrag einzurichten, erstellen Sie zwei Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-107">To create a duplex contract you create a pair of interfaces.</span></span> <span data-ttu-id="a2fde-108">Bei der ersten handelt es sich um die Dienstvertragschnittstelle, mit der die Vorgänge beschrieben werden, die von einem Client implementiert werden können.</span><span class="sxs-lookup"><span data-stu-id="a2fde-108">The first is the service contract interface that describes the operations that a client can invoke.</span></span> <span data-ttu-id="a2fde-109">Dieser Dienstvertrag muss in der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> -Eigenschaft einen *Rückruf Vertrag* angeben.</span><span class="sxs-lookup"><span data-stu-id="a2fde-109">That service contract must specify a *callback contract* in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a2fde-110">Der Rückrufvertrag wiederum ist die Schnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="a2fde-110">The callback contract is the interface that defines the operations that the service can call on the client endpoint.</span></span> <span data-ttu-id="a2fde-111">Ein Duplexvertrag erfordert keine Sitzung, die vom System bereitgestellten Duplexbindungen nutzen allerdings Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-111">A duplex contract does not require a session, although the system-provided duplex bindings make use of them.</span></span>

<span data-ttu-id="a2fde-112">Das folgende Beispiel zeigt einen Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="a2fde-112">The following is an example of a duplex contract.</span></span>

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

<span data-ttu-id="a2fde-113">Die `CalculatorService`-Klasse implementiert die primäre `ICalculatorDuplex`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a2fde-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="a2fde-114">Der Dienst verwendet den <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanzmodus, um die Ergebnisse für die einzelnen Sitzungen zu pflegen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="a2fde-115">Die private `Callback`-Eigenschaft greift auf den Rückrufkanal zu, der zum Client führt.</span><span class="sxs-lookup"><span data-stu-id="a2fde-115">A private property named `Callback` accesses the callback channel to the client.</span></span> <span data-ttu-id="a2fde-116">Der Dienst nutzt den Rückruf, um über die Rückrufschnittstelle Nachrichten zurück an den Client zu senden, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2fde-116">The service uses the callback for sending messages back to the client through the callback interface, as shown in the following sample code.</span></span>

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

<span data-ttu-id="a2fde-117">Damit Nachrichten vom Dienst empfangen werden können, muss der Client eine Klasse bereitstellen, die die Rückrufschnittstelle des Duplexvertrags implementiert.</span><span class="sxs-lookup"><span data-stu-id="a2fde-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="a2fde-118">Der folgende Beispielcode enthält eine `CallbackHandler`-Klasse, durch die die `ICalculatorDuplexCallback`-Schnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2fde-118">The following sample code shows a `CallbackHandler` class that implements the `ICalculatorDuplexCallback` interface.</span></span>

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

<span data-ttu-id="a2fde-119">Für den für einen Duplex Vertrag generierten WCF-Client muss bei <xref:System.ServiceModel.InstanceContext> der Erstellung eine-Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a2fde-119">The WCF client that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> class to be provided upon construction.</span></span> <span data-ttu-id="a2fde-120">Diese <xref:System.ServiceModel.InstanceContext>-Klasse wird als Standort für ein Objekt verwendet, das die Rückrufschnittstelle implementiert und die vom Dienst zurückgesendeten Nachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a2fde-120">This <xref:System.ServiceModel.InstanceContext> class is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="a2fde-121">Eine <xref:System.ServiceModel.InstanceContext>-Klasse wird mit einer Instanz der `CallbackHandler`-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="a2fde-121">An <xref:System.ServiceModel.InstanceContext> class is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="a2fde-122">Dieses Objekt verarbeitet die vom Dienst über die Rückrufschnittstelle an den Client gesendeten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a2fde-122">This object handles messages sent from the service to the client on the callback interface.</span></span>

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

<span data-ttu-id="a2fde-123">Der Dienst muss so konfiguriert werden, dass eine Bindung bereitgestellt wird, die sowohl eine Sitzungskommunikation als auch eine Duplexkommunikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2fde-123">The configuration for the service must be set up to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="a2fde-124">Das `wsDualHttpBinding`-Element unterstützt die sitzungsbasierte Kommunikation und ermöglicht durch Bereitstellung dualer HTTP-Verbindungen (eine Verbindung pro Richtung) auch eine Duplexkommunikation.</span><span class="sxs-lookup"><span data-stu-id="a2fde-124">The `wsDualHttpBinding` element supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span>

<span data-ttu-id="a2fde-125">Auf dem Client muss, wie in der folgenden Beispielkonfiguration zu sehen, eine Adresse konfiguriert werden, über die der Server eine Verbindung mit dem Client herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a2fde-125">On the client, you must configure an address that the server can use to connect to the client, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="a2fde-126">Nichtduplex-Clients, bei denen keine Authentifizierung über eine sichere Konversation möglich ist, lösen in der Regel eine <xref:System.ServiceModel.Security.MessageSecurityException> aus.</span><span class="sxs-lookup"><span data-stu-id="a2fde-126">Non-duplex clients that fail to authenticate using a secure conversation typically throw a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="a2fde-127">Wenn jedoch bei einem Duplexclient, der eine sichere Konversation verwendet, keine Authentifizierung möglich ist, erhält der Client stattdessen eine <xref:System.TimeoutException>.</span><span class="sxs-lookup"><span data-stu-id="a2fde-127">However, if a duplex client that uses a secure conversation fails to authenticate, the client receives a <xref:System.TimeoutException> instead.</span></span>

<span data-ttu-id="a2fde-128">Wenn Sie mit dem `WSHttpBinding`-Element einen Client/Dienst erstellen und keinen Clientrückrufendpunkt aufnehmen, wird der folgende Fehler ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="a2fde-128">If you create a client/service using the `WSHttpBinding` element and you do not include the client callback endpoint, you will receive the following error.</span></span>

```console
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

<span data-ttu-id="a2fde-129">Der folgende Beispielcode zeigt, wie Sie die clientend Punkt Adresse Programm gesteuert angeben.</span><span class="sxs-lookup"><span data-stu-id="a2fde-129">The following sample code shows how to specify the client endpoint address programmatically.</span></span>

```csharp
WSDualHttpBinding binding = new WSDualHttpBinding();
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");
```

```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")
```

<span data-ttu-id="a2fde-130">Der folgende Beispielcode zeigt, wie Sie die Clientendpunktadresse in der Konfiguration angeben können:</span><span class="sxs-lookup"><span data-stu-id="a2fde-130">The following sample code shows how to specify the client endpoint address in configuration.</span></span>

```xml
<client>
    <endpoint name ="ServerEndpoint"
          address="http://localhost:12000/DuplexTestUsingConfig/Server"
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"
            binding="wsDualHttpBinding"
           contract="IDuplexTest" />
</client>
<bindings>
    <wsDualHttpBinding>
        <binding name="WSDualHttpBinding_IDuplexTest"
          clientBaseAddress="http://localhost:8000/myClient/" >
            <security mode="None"/>
         </binding>
    </wsDualHttpBinding>
</bindings>
```

> [!WARNING]
> <span data-ttu-id="a2fde-131">Das Duplex Modell erkennt nicht automatisch, wenn ein Dienst oder Client seinen Kanal schließt.</span><span class="sxs-lookup"><span data-stu-id="a2fde-131">The duplex model doesn't automatically detect when a service or client closes its channel.</span></span> <span data-ttu-id="a2fde-132">Wenn ein Client also unerwartet beendet wird, wird der Dienst standardmäßig nicht benachrichtigt, oder wenn ein Dienst unerwartet beendet wird, wird der Client nicht benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="a2fde-132">So if a client unexpectedly terminates, by default the service will not be notified, or if a service unexpectedly terminates, the client will not be notified.</span></span> <span data-ttu-id="a2fde-133">Wenn Sie einen Dienst verwenden, der getrennt ist, <xref:System.ServiceModel.CommunicationException> wird die Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a2fde-133">If you use a service that is disconnected, the <xref:System.ServiceModel.CommunicationException> exception is raised.</span></span> <span data-ttu-id="a2fde-134">Clients und Dienste können eigene Protokolle implementieren, um sich bei Bedarf wechselseitig zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-134">Clients and services can implement their own protocol to notify each other if they so choose.</span></span> <span data-ttu-id="a2fde-135">Weitere Informationen zur Fehlerbehandlung finden Sie unter [WCF-Fehlerbehandlung](../wcf-error-handling.md) .</span><span class="sxs-lookup"><span data-stu-id="a2fde-135">For more information on error handling, see [WCF Error Handling](../wcf-error-handling.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="a2fde-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2fde-136">See also</span></span>

- [<span data-ttu-id="a2fde-137">Duplex</span><span class="sxs-lookup"><span data-stu-id="a2fde-137">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="a2fde-138">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="a2fde-138">Specifying Client Run-Time Behavior</span></span>](../specifying-client-run-time-behavior.md)
- [<span data-ttu-id="a2fde-139">Vorgehensweise: Erstellen Sie eine Kanalfactory, und verwenden Sie Sie zum Erstellen und Verwalten von Kanälen.</span><span class="sxs-lookup"><span data-stu-id="a2fde-139">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>](how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
