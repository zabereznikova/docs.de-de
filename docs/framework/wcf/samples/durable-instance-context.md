---
title: Permanenter Instanzkontext
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: d70617fef7ebe0a94e22e858ee403d5d4f1840e3
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728410"
---
# <a name="durable-instance-context"></a><span data-ttu-id="175f9-102">Permanenter Instanzkontext</span><span class="sxs-lookup"><span data-stu-id="175f9-102">Durable Instance Context</span></span>

<span data-ttu-id="175f9-103">In diesem Beispiel wird veranschaulicht, wie die Windows Communication Foundation (WCF)-Laufzeit angepasst wird, um permanente Instanzkontexte zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-103">This sample demonstrates how to customize the Windows Communication Foundation (WCF) runtime to enable durable instance contexts.</span></span> <span data-ttu-id="175f9-104">Dabei wird als Sicherungsspeicher SQL Server 2005 (in diesem Fall SQL Server 2005 Express) verwendet.</span><span class="sxs-lookup"><span data-stu-id="175f9-104">It uses SQL Server 2005 as its backing store (SQL Server 2005 Express in this case).</span></span> <span data-ttu-id="175f9-105">Aber es bietet auch eine Möglichkeit, auf benutzerdefinierte Speichermechanismen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="175f9-105">However, it also provides a way to access custom storage mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="175f9-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="175f9-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="175f9-107">Dieses Beispiel umfasst die Erweiterung der Kanal Schicht und der Dienstmodell Ebene von WCF.</span><span class="sxs-lookup"><span data-stu-id="175f9-107">This sample involves extending both the channel layer and the service model layer of the WCF.</span></span> <span data-ttu-id="175f9-108">Deshalb ist es notwendig, das zugrunde liegenden Konzept zu verstehen, bevor Sie sich mit den Implementierungsdetails beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="175f9-108">Therefore it is necessary to understand the underlying concepts before going into the implementation details.</span></span>

<span data-ttu-id="175f9-109">Permanente Instanzkontexte sind sehr häufig in realen Szenarios anzutreffen.</span><span class="sxs-lookup"><span data-stu-id="175f9-109">Durable instance contexts can be found in the real world scenarios quite often.</span></span> <span data-ttu-id="175f9-110">Eine Einkaufswagen Anwendung hat beispielsweise die Möglichkeit, den Einkauf an einem anderen Tag in der Mitte anzuhalten und fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="175f9-110">A shopping cart application, for example, has the ability to pause shopping halfway through and continue it on another day.</span></span> <span data-ttu-id="175f9-111">Wenn der Warenkorb am nächsten Tag geöffnet wird, wird der ursprüngliche Kontext wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="175f9-111">So that when we visit the shopping cart the next day, our original context is restored.</span></span> <span data-ttu-id="175f9-112">Es ist jedoch unbedingt zu beachten, dass die Warenkorb-Anwendung (auf dem Server) nicht die Warenkorb-Instanz beibehält, während die Verbindung zum Server getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="175f9-112">It is important to note that the shopping cart application (on the server) does not maintain the shopping cart instance while we are disconnected.</span></span> <span data-ttu-id="175f9-113">Sie behält vielmehr ihren Zustand in einem permanenten Speichermedium bei und verwendet diesen Zustand, wenn eine neue Instanz für den wiederhergestellten Kontext erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="175f9-113">Instead, it persists its state into a durable storage media and uses it when constructing a new instance for the restored context.</span></span> <span data-ttu-id="175f9-114">Aus diesem Grund handelt es sich bei der Dienstinstanz, die möglicherweise für denselben Kontext dient, nicht um dieselbe Instanz wie die vorherige Instanz (d. h. sie hat nicht dieselbe Speicheradresse).</span><span class="sxs-lookup"><span data-stu-id="175f9-114">Therefore the service instance that may service for the same context is not the same as the previous instance (that is, it does not have the same memory address).</span></span>

<span data-ttu-id="175f9-115">Permanenter Instanzkontext wird durch ein kleines Protokoll ermöglicht, das eine Kontext-ID zwischen dem Client und dem Dienst austauscht.</span><span class="sxs-lookup"><span data-stu-id="175f9-115">Durable instance context is made possible by a small protocol that exchanges a context ID between the client and service.</span></span> <span data-ttu-id="175f9-116">Diese Kontext-ID wird auf dem Client erstellt und zum Dienst übertragen.</span><span class="sxs-lookup"><span data-stu-id="175f9-116">This context ID is created on the client and transmitted to the service.</span></span> <span data-ttu-id="175f9-117">Wenn die Dienstinstanz erstellt wird, versucht die Dienstlaufzeit den beibehaltenen Zustand zu laden, der dieser Kontext-ID aus einer permanenten Speicherung entspricht (standardmäßig ist es eine SQL Server 2005-Datenbank).</span><span class="sxs-lookup"><span data-stu-id="175f9-117">When the service instance is created, the service runtime tries to load the persisted state that corresponds to this context ID from a persistent storage (by default it is a SQL Server 2005 database).</span></span> <span data-ttu-id="175f9-118">Wenn kein Status verfügbar ist, hat die neue Instanz ihren Standardzustand.</span><span class="sxs-lookup"><span data-stu-id="175f9-118">If no state is available, the new instance has its default state.</span></span> <span data-ttu-id="175f9-119">Die Dienstimplementierung verwendet ein benutzerdefiniertes Attribut, um Vorgänge zu kennzeichnen, die den Zustand der Dienstimplementierung ändern. Die Laufzeit kann dadurch die Dienstinstanz speichern, nachdem die Vorgänge aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="175f9-119">The service implementation uses a custom attribute to mark operations that change the state of the service implementation so that the runtime can save the service instance after invoking them.</span></span>

<span data-ttu-id="175f9-120">Anhand der vorangegangenen Beschreibung können leicht zwei Schritte bestimmt werden, um das Ziel zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="175f9-120">By the previous description, two steps can easily be distinguished to achieve the goal:</span></span>

1. <span data-ttu-id="175f9-121">Ändern Sie die Nachricht, mit der die Kontext-ID übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="175f9-121">Change the message that goes on the wire to carry the context ID.</span></span>

2. <span data-ttu-id="175f9-122">Ändern Sie das lokale Verhalten des Diensts, um die benutzerdefinierte Instanziierungslogik zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-122">Change the service local behavior to implement custom instancing logic.</span></span>

<span data-ttu-id="175f9-123">Da sich der erste in der Liste auf die Nachrichten bei der Übertragung auswirkt, sollte er als benutzerdefinierter Kanal implementiert und mit der Kanal Schicht verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-123">Because the first one in the list affects the messages on the wire, it should be implemented as a custom channel and be hooked up to the channel layer.</span></span> <span data-ttu-id="175f9-124">Der zweite Schritt beeinflusst nur das lokale Verhalten des Diensts und kann deshalb durch das Erweitern mehrerer Diensterweiterungspunkte implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-124">The latter only affects the service local behavior and therefore can be implemented by extending several service extensibility points.</span></span> <span data-ttu-id="175f9-125">In den nächsten Abschnitten wird jede dieser Erweiterungen erläutert.</span><span class="sxs-lookup"><span data-stu-id="175f9-125">In the next few sections, each of these extensions are discussed.</span></span>

## <a name="durable-instancecontext-channel"></a><span data-ttu-id="175f9-126">Permanenter InstanceContext-Kanal</span><span class="sxs-lookup"><span data-stu-id="175f9-126">Durable InstanceContext Channel</span></span>

<span data-ttu-id="175f9-127">Als erstes wird eine Kanalschichterweiterung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="175f9-127">The first thing to look at is a channel layer extension.</span></span> <span data-ttu-id="175f9-128">Der erste Schritt beim Schreiben eines benutzerdefinierten Kanals besteht darin, die Kommunikationsstruktur des Kanals festzulegen.</span><span class="sxs-lookup"><span data-stu-id="175f9-128">The first step in writing a custom channel is to decide the communication structure of the channel.</span></span> <span data-ttu-id="175f9-129">Wenn ein neues Wire-Protokoll eingeführt wird, sollte der Kanal mit fast allen anderen Kanälen im Kanal Stapel funktionieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-129">As a new wire protocol is being introduced, the channel should work with almost any other channel in the channel stack.</span></span> <span data-ttu-id="175f9-130">Deshalb sollte es alle Nachrichtenaustauschmuster unterstützen.</span><span class="sxs-lookup"><span data-stu-id="175f9-130">Therefore it should support all the message exchange patterns.</span></span> <span data-ttu-id="175f9-131">Die Kernfunktionalität des Kanals ändert sich jedoch nicht, unabhängig von seiner Kommunikationsstruktur.</span><span class="sxs-lookup"><span data-stu-id="175f9-131">However, the core functionality of the channel is the same regardless of its communication structure.</span></span> <span data-ttu-id="175f9-132">Genauer gesagt sollte der Kanal vom Client die Kontext-ID in die Nachrichten schreiben und vom Dienst sollte er diese Kontext-ID aus den Nachrichten lesen und an die höheren Ebenen weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="175f9-132">More specifically, from the client it should write the context ID to the messages and from the service it should read this context ID from the messages and pass it to the upper levels.</span></span> <span data-ttu-id="175f9-133">Aus diesem Grund wird eine `DurableInstanceContextChannelBase`-Klasse erstellt, die als die abstrakte Basisklasse für alle Implementierungen von permanenten Instanzkontext-Kanälen handelt.</span><span class="sxs-lookup"><span data-stu-id="175f9-133">Because of that, a `DurableInstanceContextChannelBase` class is created that acts as the abstract base class for all durable instance context channel implementations.</span></span> <span data-ttu-id="175f9-134">Diese Klasse enthält die allgemeinen Computerverwaltungsfunktionen und zwei geschützte Member, um die Kontextinformationen auf Nachrichten anzuwenden und von ihnen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="175f9-134">This class contains the common state machine management functions and two protected members to apply and read the context information to and from messages.</span></span>

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

<span data-ttu-id="175f9-135">Diese beiden Methoden nutzen `IContextManager`-Implementierungen, um die Kontext-ID auf Nachrichten zu schreiben und von ihnen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="175f9-135">These two methods make use of `IContextManager` implementations to write and read the context ID to or from the message.</span></span> <span data-ttu-id="175f9-136">(`IContextManager` eine benutzerdefinierte Schnittstelle, die verwendet wird, um den Vertrag für alle Kontext-Manager zu definieren.) Der Kanal kann entweder die Kontext-ID in einem benutzerdefinierten SOAP-Header oder in einem HTTP-Cookie-Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="175f9-136">(`IContextManager` is a custom interface used to define the contract for all context managers.) The channel can either include the context ID in a custom SOAP header or in an HTTP cookie header.</span></span> <span data-ttu-id="175f9-137">Jede Kontextmanagerimplementierung erbt von der `ContextManagerBase`-Klasse, die die allgemeine Funktionalität für alle Kontextmanager enthält.</span><span class="sxs-lookup"><span data-stu-id="175f9-137">Each context manager implementation inherits from the `ContextManagerBase` class that contains the common functionality for all context managers.</span></span> <span data-ttu-id="175f9-138">Die `GetContextId`-Methode in dieser Klasse wird verwendet, um die Kontext-ID vom Client zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="175f9-138">The `GetContextId` method in this class is used to originate the context ID from the client.</span></span> <span data-ttu-id="175f9-139">Wenn eine Kontext-ID ist zum ersten Mal erzeugt wird, wird sie mithilfe dieser Methode in einer Textdatei gespeichert, deren Name von der Remote-Endpunktadresse erstellt wird (in den typischen URI werden ungültige Zeichen im Dateinamen durch @-Zeichen ersetzt).</span><span class="sxs-lookup"><span data-stu-id="175f9-139">When a context ID is originated for the first time, this method saves it into a text file whose name is constructed by the remote endpoint address (the invalid file name characters in the typical URIs are replaced with @ characters).</span></span>

<span data-ttu-id="175f9-140">Wird die Kontext-ID später für denselben Remote-Endpunkt benötigt, überprüft diese Methode, ob eine entsprechende Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="175f9-140">Later when the context ID is required for the same remote endpoint, it checks whether an appropriate file exists.</span></span> <span data-ttu-id="175f9-141">Wenn dies der Fall ist, liest sie die Kontext-ID und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="175f9-141">If it does, it reads the context ID and returns.</span></span> <span data-ttu-id="175f9-142">Andernfalls gibt sie eine neu generierte Kontext-ID zurück und speichert sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="175f9-142">Otherwise it returns a newly generated context ID and saves it to a file.</span></span> <span data-ttu-id="175f9-143">Mit der Standardkonfiguration werden diese Dateien in einem Verzeichnis namens "contextstore" abgelegt, das sich im temporären Verzeichnis des aktuellen Benutzers befindet.</span><span class="sxs-lookup"><span data-stu-id="175f9-143">With the default configuration, these files are placed in a directory called ContextStore, which resides in the current user's temp directory.</span></span> <span data-ttu-id="175f9-144">Dieser Speicherort ist jedoch mit dem Bindungselement konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="175f9-144">However this location is configurable using the binding element.</span></span>

<span data-ttu-id="175f9-145">Der für den Transport der Kontext-ID verwendete Mechanismus kann konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-145">The mechanism used to transport the context ID is configurable.</span></span> <span data-ttu-id="175f9-146">Er kann entweder in den HTTP-Cookieheader oder einen benutzerdefinierten SOAP-Header geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-146">It could be either written to the HTTP cookie header or to a custom SOAP header.</span></span> <span data-ttu-id="175f9-147">Wenn Sie sich für den benutzerdefinierten SOAP-Header entscheiden, kann dieses Protokoll mit anderen als HTTP-Protokollen (z. B. TCP oder Benannte Pipes) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-147">The custom SOAP header approach makes it possible to use this protocol with non-HTTP protocols (for example, TCP or Named Pipes).</span></span> <span data-ttu-id="175f9-148">Es gibt zwei Klassen, nämlich `MessageHeaderContextManager` und `HttpCookieContextManager`, die diese beiden Optionen implementieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-148">There are two classes, namely `MessageHeaderContextManager` and `HttpCookieContextManager`, which implement these two options.</span></span>

<span data-ttu-id="175f9-149">Beide Klassen schreiben die Kontext-ID richtig in die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="175f9-149">Both of them write the context ID to the message appropriately.</span></span> <span data-ttu-id="175f9-150">Die `MessageHeaderContextManager`-Klasse schreibt sie beispielsweise in einen SOAP-Header in der `WriteContext`-Methode.</span><span class="sxs-lookup"><span data-stu-id="175f9-150">For example, the `MessageHeaderContextManager` class writes it to a SOAP header in the `WriteContext` method.</span></span>

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

<span data-ttu-id="175f9-151">Sowohl die `ApplyContext`-Methode als auch die `ReadContextId`-Methode in der `DurableInstanceContextChannelBase`-Klasse rufen `IContextManager.ReadContext` bzw. `IContextManager.WriteContext` auf.</span><span class="sxs-lookup"><span data-stu-id="175f9-151">Both the `ApplyContext` and `ReadContextId` methods in the `DurableInstanceContextChannelBase` class invoke the `IContextManager.ReadContext` and `IContextManager.WriteContext`, respectively.</span></span> <span data-ttu-id="175f9-152">Diese Kontext-Manager werden jedoch nicht direkt von der `DurableInstanceContextChannelBase`-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="175f9-152">However, these context managers are not directly created by the `DurableInstanceContextChannelBase` class.</span></span> <span data-ttu-id="175f9-153">Diese Aufgabe wird von der `ContextManagerFactory`-Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="175f9-153">Instead it uses the `ContextManagerFactory` class to do that job.</span></span>

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

<span data-ttu-id="175f9-154">Die `ApplyContext`-Methode wird von den Sendekanälen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="175f9-154">The `ApplyContext` method is invoked by the sending channels.</span></span> <span data-ttu-id="175f9-155">Sie fügt die Kontext-ID in die ausgehenden Nachrichten ein.</span><span class="sxs-lookup"><span data-stu-id="175f9-155">It injects the context ID to the outgoing messages.</span></span> <span data-ttu-id="175f9-156">Die `ReadContextId`-Methode wird von den Empfangskanälen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="175f9-156">The `ReadContextId` method is invoked by the receiving channels.</span></span> <span data-ttu-id="175f9-157">Diese Methode stellt sicher, dass die Kontext-ID in den eingehenden Nachrichten verfügbar ist und fügt sie zur `Properties`-Auflistung der `Message`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="175f9-157">This method ensures that the context ID is available in the incoming messages and adds it to the `Properties` collection of the `Message` class.</span></span> <span data-ttu-id="175f9-158">Wenn ein Fehler beim Lesen der Kontext-ID auftritt und der Kanal abgebrochen wird, löst diese Methode eine `CommunicationException` aus.</span><span class="sxs-lookup"><span data-stu-id="175f9-158">It also throws a `CommunicationException` in case of a failure to read the context ID and thus causes the channel to be aborted.</span></span>

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

<span data-ttu-id="175f9-159">Bevor Sie fortfahren, ist es wichtig, die Verwendung der `Properties`-Auflistung in der `Message`-Klasse zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="175f9-159">Before proceeding, it is important to understand the usage of the `Properties` collection in the `Message` class.</span></span> <span data-ttu-id="175f9-160">In der Regel wird diese `Properties`-Auflistung verwendet, wenn Daten von unteren an die obere Ebenen der Kanalschicht weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-160">Typically, this `Properties` collection is used when passing data from lower to the upper levels from the channel layer.</span></span> <span data-ttu-id="175f9-161">So können die gewünschten Daten den oberen Ebenen konsistent und unabhängig von den Protokolldetails zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-161">This way the desired data can be provided to the upper levels in a consistent manner regardless of the protocol details.</span></span> <span data-ttu-id="175f9-162">Das heißt, die Kanal Ebene kann die Kontext-ID senden und als SOAP-Header oder HTTP-Cookie-Header empfangen.</span><span class="sxs-lookup"><span data-stu-id="175f9-162">In other words, the channel layer can send and receive the context ID either as a SOAP header or an HTTP cookie header.</span></span> <span data-ttu-id="175f9-163">Die oberen Ebenen müssen diese Details jedoch nicht kennen, da die Kanalschicht diese Informationen in der `Properties`-Auflistung verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="175f9-163">But it is not necessary for the upper levels to know about these details because the channel layer makes this information available in the `Properties` collection.</span></span>

<span data-ttu-id="175f9-164">Wenn die `DurableInstanceContextChannelBase`-Klasse vorhanden ist, müssen alle zehn erforderlichen Schnittstellen (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-164">Now with the `DurableInstanceContextChannelBase` class in place all ten of the necessary interfaces (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) must be implemented.</span></span> <span data-ttu-id="175f9-165">Sie ähneln jedem verfügbaren Nachrichtenaustausch Muster (Datagram, Simplex, Duplex und ihren Sitzungs basierten Varianten).</span><span class="sxs-lookup"><span data-stu-id="175f9-165">They resemble every available message exchange pattern (datagram, simplex, duplex, and their sessionful variants).</span></span> <span data-ttu-id="175f9-166">Jede dieser Implementierungen erbt die zuvor beschriebene Basisklasse und ruft `ApplyContext` und `ReadContextId` entsprechend auf.</span><span class="sxs-lookup"><span data-stu-id="175f9-166">Each of these implementations inherits the base class previously described and calls `ApplyContext` and `ReadContextId` appropriately.</span></span> <span data-ttu-id="175f9-167">So ruft beispielsweise `DurableInstanceContextOutputChannel` – die die IOutputChannel-Schnittstelle implementiert – die `ApplyContext`-Methode von jeder Methode auf, die Nachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="175f9-167">For example, `DurableInstanceContextOutputChannel` - which implements the IOutputChannel interface - calls the `ApplyContext` method from each method that sends the messages.</span></span>

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

<span data-ttu-id="175f9-168">Auf der anderen Seite, `DurableInstanceContextInputChannel` die die `IInputChannel` -Schnittstelle implementiert, ruft `ReadContextId` die-Methode in jeder Methode auf, die die Nachrichten empfängt.</span><span class="sxs-lookup"><span data-stu-id="175f9-168">On the other hand, `DurableInstanceContextInputChannel` - which implements the `IInputChannel` interface - calls the `ReadContextId` method in each method, which receives the messages.</span></span>

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

<span data-ttu-id="175f9-169">Außerdem delegieren diese Kanalimplementierungen die Methodenaufrufe an den nächst unteren Kanal im Kanalstapel.</span><span class="sxs-lookup"><span data-stu-id="175f9-169">Apart from this, these channel implementations delegate the method invocations to the channel below them in the channel stack.</span></span> <span data-ttu-id="175f9-170">Sitzungsbasierte Varianten verfügen jedoch über eine Grundlogik, um sicherzustellen, dass die Kontext-ID gesendet und nur für die erste Nachricht gelesen wird, aufgrund derer die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="175f9-170">However, sessionful variants have a basic logic to make sure that the context ID is sent and is read only for the first message that causes the session to be created.</span></span>

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

<span data-ttu-id="175f9-171">Diese Channelimplementierungen werden dann der WCF-Channel-Laufzeit von der `DurableInstanceContextBindingElement` -Klasse `DurableInstanceContextBindingElementSection` und der-Klasse entsprechend hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="175f9-171">These channel implementations are then added to the WCF channel runtime by the `DurableInstanceContextBindingElement` class and `DurableInstanceContextBindingElementSection` class appropriately.</span></span> <span data-ttu-id="175f9-172">Weitere Informationen zu Bindungs Elementen und Bindungs Element Abschnitten finden Sie in der Beispiel Dokumentation zum [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) -Channel.</span><span class="sxs-lookup"><span data-stu-id="175f9-172">See the [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) channel sample documentation for more details about binding elements and binding element sections.</span></span>

## <a name="service-model-layer-extensions"></a><span data-ttu-id="175f9-173">Erweiterungen der Dienstmodellebene</span><span class="sxs-lookup"><span data-stu-id="175f9-173">Service Model Layer Extensions</span></span>

<span data-ttu-id="175f9-174">Nachdem nun die Kontext-ID die Kanalschicht durchlaufen hat, kann das Dienstverhalten implementiert werden, um die Instanziierung benutzerspezifisch anzupassen.</span><span class="sxs-lookup"><span data-stu-id="175f9-174">Now that the context ID has traveled through the channel layer, the service behavior can be implemented to customize the instantiation.</span></span> <span data-ttu-id="175f9-175">In diesem Beispiel wird ein Speicher-Manager verwendet, um den Zustand aus dem permanenten Speicher zu laden und in ihm zu speichern.</span><span class="sxs-lookup"><span data-stu-id="175f9-175">In this sample, a storage manager is used to load and save state from or to the persistent store.</span></span> <span data-ttu-id="175f9-176">Wie bereits erläutert arbeitet dieses Beispiel mit einem Speicher-Manager, der SQL Server 2005 als Sicherungsspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="175f9-176">As explained previously, this sample provides a storage manager that uses SQL Server 2005 as its backing store.</span></span> <span data-ttu-id="175f9-177">Es ist aber auch möglich, benutzerdefinierte Speichermechanismen zu dieser Erweiterung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="175f9-177">However, it is also possible to add custom storage mechanisms to this extension.</span></span> <span data-ttu-id="175f9-178">Dazu wird eine öffentliche Schnittstelle deklariert, die von allen Speicher-Managern implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="175f9-178">To do that a public interface is declared, which must be implemented by all storage managers.</span></span>

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

<span data-ttu-id="175f9-179">Die `SqlServerStorageManager`-Klasse enthält die `IStorageManager`-Standardimplementierung.</span><span class="sxs-lookup"><span data-stu-id="175f9-179">The `SqlServerStorageManager` class contains the default `IStorageManager` implementation.</span></span> <span data-ttu-id="175f9-180">In der `SaveInstance` -Methode wird das angegebene Objekt mit dem XmlSerializer serialisiert und in der SQL Server-Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="175f9-180">In its `SaveInstance` method, the given object is serialized using the XmlSerializer and is saved to the SQL Server database.</span></span>

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

<span data-ttu-id="175f9-181">In der `GetInstance` -Methode werden die serialisierten Daten für eine angegebene Kontext-ID gelesen, und das Objekt, das daraus erstellt wird, wird an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="175f9-181">In the `GetInstance` method, the serialized data is read for a given context ID and the object constructed from it is returned to the caller.</span></span>

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

<span data-ttu-id="175f9-182">Benutzer dieser Speicher-Manager sollten sie nicht direkt instanziieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-182">Users of these storage managers are not supposed to instantiate them directly.</span></span> <span data-ttu-id="175f9-183">Sie verwenden die `StorageManagerFactory`-Klasse, die von den Speichermanagererstellungsdetails abstrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="175f9-183">They use the `StorageManagerFactory` class, which abstracts from the storage manager creation details.</span></span> <span data-ttu-id="175f9-184">Diese Klasse verfügt über einen statischen Member, `GetStorageManager`, der eine Instanz eines gegebenen Speichermanagertyps erstellt.</span><span class="sxs-lookup"><span data-stu-id="175f9-184">This class has one static member, `GetStorageManager`, which creates an instance of a given storage manager type.</span></span> <span data-ttu-id="175f9-185">Wenn der Typparameter `null` lautet, erstellt diese Methode eine Instanz der `SqlServerStorageManager`-Standardklasse und gibt diese zurück.</span><span class="sxs-lookup"><span data-stu-id="175f9-185">If the type parameter is `null`, this method creates an instance of the default `SqlServerStorageManager` class and returns it.</span></span> <span data-ttu-id="175f9-186">Sie überprüft auch den gegebenen Typ, um sicherzustellen, dass er die `IStorageManager`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-186">It also validates the given type to make sure that it implements the `IStorageManager` interface.</span></span>

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

<span data-ttu-id="175f9-187">Die notwendige Infrastruktur zum Lesen und Schreiben von Instanzen aus dem permanenten Speicher wurde implementiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-187">The necessary infrastructure to read and write instances from the persistent storage is implemented.</span></span> <span data-ttu-id="175f9-188">Jetzt müssen die notwendigen Schritte zum Ändern des Dienstverhaltens durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-188">Now the necessary steps to change the service behavior have to be taken.</span></span>

<span data-ttu-id="175f9-189">Zuerst muss die Kontext-ID gespeichert werden, die über die Kanalschicht zur aktuellen InstanceContext übertragen wurde.</span><span class="sxs-lookup"><span data-stu-id="175f9-189">As the first step of this process we have to save the context ID, which came through the channel layer to the current InstanceContext.</span></span> <span data-ttu-id="175f9-190">InstanceContext ist eine Laufzeitkomponente, die als Link zwischen dem WCF-Verteiler und der Dienst Instanz fungiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-190">InstanceContext is a runtime component that acts as the link between the WCF dispatcher and the service instance.</span></span> <span data-ttu-id="175f9-191">Sie kann verwendet werden, um der Dienstinstanz einen zusätzlichen Zustand und zusätzliches Verhalten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="175f9-191">It can be used to provide additional state and behavior to the service instance.</span></span> <span data-ttu-id="175f9-192">Dies ist notwendig, da die Kontext-ID in einer sitzungsbasierten Kommunikation nur mit der ersten Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="175f9-192">This is essential because in sessionful communication the context ID is sent only with the first message.</span></span>

<span data-ttu-id="175f9-193">WCF ermöglicht die Erweiterung der InstanceContext-Laufzeitkomponente durch Hinzufügen eines neuen Zustands und Verhaltens mithilfe des erweiterbaren Objekt Musters.</span><span class="sxs-lookup"><span data-stu-id="175f9-193">WCF allows extending its InstanceContext runtime component by adding a new state and behavior using its extensible object pattern.</span></span> <span data-ttu-id="175f9-194">Das Extensible Object-Muster wird in WCF verwendet, um vorhandene Lauf Zeit Klassen um neue Funktionen zu erweitern oder um neue Zustands Funktionen zu einem Objekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="175f9-194">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="175f9-195">Es gibt drei Schnittstellen im erweiterbaren Objektmuster: IExtensibleObject\<t>, IExtension\<t> und IExtensionCollection\<t>:</span><span class="sxs-lookup"><span data-stu-id="175f9-195">There are three interfaces in the extensible object pattern - IExtensibleObject\<T>, IExtension\<T>, and IExtensionCollection\<T>:</span></span>

- <span data-ttu-id="175f9-196">Die IExtensibleObject\<T->-Schnittstelle wird von Objekten implementiert, die Erweiterungen zulassen, die ihre Funktionalität anpassen.</span><span class="sxs-lookup"><span data-stu-id="175f9-196">The IExtensibleObject\<T> interface is implemented by objects that allow extensions that customize their functionality.</span></span>

- <span data-ttu-id="175f9-197">Die IExtension\<T>-Schnittstelle wird von Objekten implementiert, die Erweiterungen von Klassen des Typs t sind.</span><span class="sxs-lookup"><span data-stu-id="175f9-197">The IExtension\<T> interface is implemented by objects that are extensions of classes of type T.</span></span>

- <span data-ttu-id="175f9-198">Die IExtensionCollection\<T->-Schnittstelle ist eine Auflistung von iextensions, die das Abrufen von iextensions nach ihrem Typ ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="175f9-198">The IExtensionCollection\<T> interface is a collection of IExtensions that allows for retrieving IExtensions by their type.</span></span>

<span data-ttu-id="175f9-199">Es sollte deshalb eine InstanceContextExtension-Klasse erstellt werden, die die IExtension-Schnittstelle implementiert und den erforderlichen Zustand zum Speichern der Kontext-ID definiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-199">Therefore an InstanceContextExtension class should be created that implements the IExtension interface and defines the required state to save the context ID.</span></span> <span data-ttu-id="175f9-200">Diese Klasse bietet auch den Zustand, um den verwendeten Speicher-Manager aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="175f9-200">This class also provides the state to hold the storage manager being used.</span></span> <span data-ttu-id="175f9-201">Sobald der neue Zustand gespeichert ist, sollte es nicht mehr möglich sein, ihn zu ändern.</span><span class="sxs-lookup"><span data-stu-id="175f9-201">Once the new state is saved, it should not be possible to modify it.</span></span> <span data-ttu-id="175f9-202">Deshalb wird der Zustand zum Erstellungszeitpunkt bereitgestellt und in der Instanz gespeichert. Anschließend kann nur über schreibgeschützte Eigenschaften darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-202">Therefore the state is provided and saved to the instance at the time it is being constructed and then only accessible using read-only properties.</span></span>

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

<span data-ttu-id="175f9-203">Die InstanceContextInitializer-Klasse implementiert die IInstanceContextInitializer-Schnittstelle und fügt die Instanzkontexterweiterung zur Erweiterungsauflistung der erstellten Komponente InstanceContext hinzu.</span><span class="sxs-lookup"><span data-stu-id="175f9-203">The InstanceContextInitializer class implements the IInstanceContextInitializer interface and adds the instance context extension to the Extensions collection of the InstanceContext being constructed.</span></span>

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

<span data-ttu-id="175f9-204">Wie bereits beschrieben wird die Kontext-ID von der `Properties`-Auflistung der `Message`-Klasse gelesen und an den Konstruktor der Erweiterungsklasse weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="175f9-204">As described earlier the context ID is read from the `Properties` collection of the `Message` class and passed to the constructor of the extension class.</span></span> <span data-ttu-id="175f9-205">Dadurch wird veranschaulicht, wie Informationen zwischen den Schichten konsistent ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="175f9-205">This demonstrates how information can be exchanged between the layers in a consistent manner.</span></span>

<span data-ttu-id="175f9-206">Im nächsten wichtigen Schritt wird der Vorgang zum Erstellen der Dienstinstanz überschrieben.</span><span class="sxs-lookup"><span data-stu-id="175f9-206">The next important step is overriding the service instance creation process.</span></span> <span data-ttu-id="175f9-207">WCF ermöglicht die Implementierung von benutzerdefinierten Instanziierungsverhaltensweisen und das Einbinden dieser Verhaltensweisen in die Laufzeit mithilfe der IInstanceProvider-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="175f9-207">WCF allows implementing custom instantiation behaviors and hooking them up to the runtime using the IInstanceProvider interface.</span></span> <span data-ttu-id="175f9-208">Die neue `InstanceProvider`-Klasse wird implementiert, um diese Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="175f9-208">The new `InstanceProvider` class is implemented to do that job.</span></span> <span data-ttu-id="175f9-209">Der vom Instanzanbieter erwartete Diensttyp wird im Konstruktor akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-209">The service type expected from the instance provider is accepted in the constructor.</span></span> <span data-ttu-id="175f9-210">Später wird dies verwendet, um neue Instanzen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="175f9-210">Later this is used to create new instances.</span></span> <span data-ttu-id="175f9-211">In der `GetInstance` -Implementierung wird eine Instanz eines Speicher-Managers erstellt, die nach einer permanenten Instanz sucht.</span><span class="sxs-lookup"><span data-stu-id="175f9-211">In the `GetInstance` implementation, an instance of a storage manager is created looking for a persisted instance.</span></span> <span data-ttu-id="175f9-212">Wenn zurück `null`gegeben wird, wird eine neue Instanz des Dienst Typs instanziiert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="175f9-212">If it returns `null`, then a new instance of the service type is instantiated and returned to the caller.</span></span>

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

<span data-ttu-id="175f9-213">Der nächste wichtige Schritt besteht darin, die `InstanceContextExtension`- `InstanceContextInitializer`,- `InstanceProvider` und-Klassen in der Dienstmodell Laufzeit zu installieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-213">The next important step is to install the `InstanceContextExtension`, `InstanceContextInitializer`, and `InstanceProvider` classes into the service model runtime.</span></span> <span data-ttu-id="175f9-214">Es kann ein benutzerdefiniertes Attribut verwendet werden, um die Dienstimplementierungsklassen für die Installation des Verhaltens zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="175f9-214">A custom attribute could be used to mark the service implementation classes to install the behavior.</span></span> <span data-ttu-id="175f9-215">`DurableInstanceContextAttribute` enthält die Implementierung für dieses Attribut und implementiert die `IServiceBehavior`-Schnittstelle, um die gesamte Dienstlaufzeit zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="175f9-215">The `DurableInstanceContextAttribute` contains the implementation for this attribute and it implements the `IServiceBehavior` interface to extend the entire service runtime.</span></span>

<span data-ttu-id="175f9-216">Diese Klasse verfügt über eine Eigenschaft, die den Typ des zu verwendenden Speicher-Managers akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-216">This class has a property that accepts the type of the storage manager to be used.</span></span> <span data-ttu-id="175f9-217">Auf diese Weise ermöglicht die-Implementierung den Benutzern, ihre eigene `IStorageManager` Implementierung als Parameter dieses Attributs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="175f9-217">In this way, the implementation enables the users to specify their own `IStorageManager` implementation as parameter of this attribute.</span></span>

<span data-ttu-id="175f9-218">In der `ApplyDispatchBehavior` -Implementierung wird `InstanceContextMode` der des aktuellen `ServiceBehavior` Attributs überprüft.</span><span class="sxs-lookup"><span data-stu-id="175f9-218">In the `ApplyDispatchBehavior` implementation, the `InstanceContextMode` of the current `ServiceBehavior` attribute is being verified.</span></span> <span data-ttu-id="175f9-219">Wenn diese Eigenschaft auf "Singleton" festgelegt ist, kann keine permanente Instanziierung aktualisiert werden und `InvalidOperationException` wird ausgelöst, um den Host zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="175f9-219">If this property is set to Singleton, enabling durable instancing is not possible and an `InvalidOperationException` is thrown to notify the host.</span></span>

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

<span data-ttu-id="175f9-220">Anschließend werden die Instanzen des Speicher-Managers, des Instanzkontextinitialisierers und des Instanzenanbieters erstellt und in der für jeden Endpunkt erstellten `DispatchRuntime` installiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-220">After this the instances of the storage manager, instance context initializer, and the instance provider are created and installed in the `DispatchRuntime` created for every endpoint.</span></span>

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

<span data-ttu-id="175f9-221">Bisher resultiert aus diesem Beispiel ein Kanal, der das benutzerdefinierte Versandprotokoll für den Austausch der benutzerdefinierten Kontext-ID aktiviert hat. Außerdem überschreibt es das Standardinstanziierungsverhalten, die Instanzen aus dem permanenten Speicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="175f9-221">In summary so far, this sample has produced a channel that enabled the custom wire protocol for custom context ID exchange and it also overwrites the default instancing behavior to load the instances from the persistent storage.</span></span>

<span data-ttu-id="175f9-222">Nun muss nur noch die Dienstinstanz im permanenten Speicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-222">What is left is a way to save the service instance to the persistent storage.</span></span> <span data-ttu-id="175f9-223">Wie zuvor erläutert gibt es bereits die erforderliche Funktionalität, den Zustand in einer `IStorageManager`-Implementierung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="175f9-223">As discussed previously, there is already the required functionality to save the state in an `IStorageManager` implementation.</span></span> <span data-ttu-id="175f9-224">Wir müssen dies jetzt in die WCF-Laufzeit integrieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-224">We now must integrate this with the WCF runtime.</span></span> <span data-ttu-id="175f9-225">Es ist ein weiteres Attribut erforderlich, dass auf die Methoden in der Dienstimplementierungsklasse angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="175f9-225">Another attribute is required that is applicable to the methods in the service implementation class.</span></span> <span data-ttu-id="175f9-226">Dieses Attribut soll auf die Methoden angewendet werden, die den Zustand der Dienstinstanz ändern.</span><span class="sxs-lookup"><span data-stu-id="175f9-226">This attribute is supposed to be applied to the methods that change the state of the service instance.</span></span>

<span data-ttu-id="175f9-227">Die `SaveStateAttribute`-Klasse implementiert diese Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="175f9-227">The `SaveStateAttribute` class implements this functionality.</span></span> <span data-ttu-id="175f9-228">Außerdem implementiert `IOperationBehavior` es die-Klasse, um die WCF-Laufzeit für jeden Vorgang zu ändern.</span><span class="sxs-lookup"><span data-stu-id="175f9-228">It also implements `IOperationBehavior` class to modify the WCF runtime for each operation.</span></span> <span data-ttu-id="175f9-229">Wenn eine Methode mit diesem Attribut markiert ist, ruft die WCF-Laufzeit `ApplyBehavior` die-Methode auf `DispatchOperation` , während die entsprechende erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="175f9-229">When a method is marked with this attribute, the WCF runtime invokes the `ApplyBehavior` method while the appropriate `DispatchOperation` is being constructed.</span></span> <span data-ttu-id="175f9-230">Diese Methoden Implementierung enthält eine einzelne Codezeile:</span><span class="sxs-lookup"><span data-stu-id="175f9-230">There is a single line of code in this method implementation:</span></span>

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

<span data-ttu-id="175f9-231">Die Anweisung erstellt eine Instanz des `OperationInvoker`-Typs und weist sie zur `Invoker`-Eigenschaft des erstellten `DispatchOperation` zu.</span><span class="sxs-lookup"><span data-stu-id="175f9-231">This instruction creates an instance of `OperationInvoker` type and assigns it to the `Invoker` property of the `DispatchOperation` being constructed.</span></span> <span data-ttu-id="175f9-232">Die `OperationInvoker`-Klasse ist ein Wrapper des Standardvorgangaufrufers, der für `DispatchOperation` erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="175f9-232">The `OperationInvoker` class is a wrapper for the default operation invoker created for the `DispatchOperation`.</span></span> <span data-ttu-id="175f9-233">Diese Klasse implementiert die `IOperationInvoker`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="175f9-233">This class implements the `IOperationInvoker` interface.</span></span> <span data-ttu-id="175f9-234">In der `Invoke` Methoden Implementierung wird der tatsächliche Methodenaufruf an den inneren Vorgangs Aufruf delegiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-234">In the `Invoke` method implementation, the actual method invocation is delegated to the inner operation invoker.</span></span> <span data-ttu-id="175f9-235">Bevor die Ergebnisse jedoch zurückgegeben werden, wird mit dem Speicher-Manager in `InstanceContext` die Dienstinstanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="175f9-235">However, before returning the results the storage manager in the `InstanceContext` is used to save the service instance.</span></span>

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a><span data-ttu-id="175f9-236">Verwenden der Erweiterung</span><span class="sxs-lookup"><span data-stu-id="175f9-236">Using the Extension</span></span>

<span data-ttu-id="175f9-237">Die Erweiterungen der channelschicht und der Dienstmodell Ebene sind abgeschlossen und können nun in WCF-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-237">Both the channel layer and service model layer extensions are done and they can now be used in WCF applications.</span></span> <span data-ttu-id="175f9-238">Dienste müssen den Kanal mithilfe einer benutzerdefinierten Bindung zum Kanal Stapel hinzufügen und dann die Dienst Implementierungsklassen mit den entsprechenden Attributen markieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-238">Services must add the channel into the channel stack using a custom binding and then mark the service implementation classes with the appropriate attributes.</span></span>

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

<span data-ttu-id="175f9-239">Clientanwendungen müssen den DurableInstanceContextChannel mit einer benutzerdefinierten Bindung zum Kanalstapel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="175f9-239">Client applications must add the DurableInstanceContextChannel into the channel stack using a custom binding.</span></span> <span data-ttu-id="175f9-240">Um den Kanal deklarativ in der Konfigurationsdatei zu konfigurieren, muss der Bindungselementbereich zur Auflistung der Bindungselementerweiterungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-240">To configure the channel declaratively in the configuration file, the binding element section has to be added to the binding element extensions collection.</span></span>

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
</system.serviceModel>
```

<span data-ttu-id="175f9-241">Jetzt kann das Bindungselement wie andere Standardbindungselemente mit einer benutzerdefinierten Bindung verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="175f9-241">Now the binding element can be used with a custom binding just like other standard binding elements:</span></span>

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a><span data-ttu-id="175f9-242">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="175f9-242">Conclusion</span></span>

<span data-ttu-id="175f9-243">In diesem Beispiel wurde gezeigt, wie ein benutzerdefinierter Protokollkanal erstellt wird und wie das Dienstverhalten angepasst werden muss, um diesen Protokollkanal zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-243">This sample showed how to create a custom protocol channel and how to customize the service behavior to enable it.</span></span>

<span data-ttu-id="175f9-244">Die Erweiterung kann weiter verbessert werden, wenn Benutzer die `IStorageManager`-Implementierung mit einem Konfigurationsabschnitt angeben können.</span><span class="sxs-lookup"><span data-stu-id="175f9-244">The extension can be further improved by letting users specify the `IStorageManager` implementation using a configuration section.</span></span> <span data-ttu-id="175f9-245">Dadurch kann der Sicherungsspeicher geändert werden, ohne den Dienstcode neu zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="175f9-245">This makes it possible to modify the backing store without recompiling the service code.</span></span>

<span data-ttu-id="175f9-246">Außerdem können Sie versuchen, eine Klasse zu implementieren (z. B. `StateBag`), die den Zustand der Instanz kapselt.</span><span class="sxs-lookup"><span data-stu-id="175f9-246">Furthermore you could try to implement a class (for example, `StateBag`), which encapsulates the state of the instance.</span></span> <span data-ttu-id="175f9-247">Diese Klasse ist für das Beibehalten des Zustands verantwortlich, wenn er sich ändert.</span><span class="sxs-lookup"><span data-stu-id="175f9-247">That class is responsible for persisting the state whenever it changes.</span></span> <span data-ttu-id="175f9-248">Sie können so die Verwendung des `SaveState`-Attributs vermeiden und die bestehenden Aufgaben genauer ausführen (Sie können z. B. den Zustand beibehalten, wenn der Zustand geändert wird, anstatt ihn jedes Mal zu speichern, wenn eine Methode mit dem `SaveState`-Attribut aufgerufen wird).</span><span class="sxs-lookup"><span data-stu-id="175f9-248">This way you can avoid using the `SaveState` attribute and perform the persisting work more accurately (for example, you could persist the state when the state is actually changed rather than saving it each time when a method with the `SaveState` attribute is called).</span></span>

<span data-ttu-id="175f9-249">Wenn Sie das Beispiel ausführen, wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="175f9-249">When you run the sample, the following output is displayed.</span></span> <span data-ttu-id="175f9-250">Der Client fügt zwei Elemente zum Warenkorb hinzu und erhält dann vom Dienst die Liste der Elemente im Warenkorb.</span><span class="sxs-lookup"><span data-stu-id="175f9-250">The client adds two items to its shopping cart and then gets the list of items in its shopping cart from the service.</span></span> <span data-ttu-id="175f9-251">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="175f9-251">Press ENTER in each console window to shut down the service and client.</span></span>

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> <span data-ttu-id="175f9-252">Durch erneutes Erstellen des Diensts wird die Datenbankdatei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="175f9-252">Rebuilding the service overwrites the database file.</span></span> <span data-ttu-id="175f9-253">Wenn Sie den Zustand überwachen möchten, der während mehrerer Durchläufe des Beispiels beibehalten wurde, erstellen Sie das Beispiel zwischen den einzelnen Durchläufen nicht neu.</span><span class="sxs-lookup"><span data-stu-id="175f9-253">To observe state preserved across multiple runs of the sample, be sure not to rebuild the sample between runs.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="175f9-254">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="175f9-254">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="175f9-255">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="175f9-255">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="175f9-256">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="175f9-256">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="175f9-257">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="175f9-257">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="175f9-258">Um dieses Beispiel auszuführen, muss SQL Server 2005 oder SQL Express 2005 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="175f9-258">You must be running SQL Server 2005 or SQL Express 2005 to run this sample.</span></span> <span data-ttu-id="175f9-259">Wenn Sie SQL Server 2005 ausführen, müssen Sie die Konfiguration der Verbindungszeichenfolge des Diensts ändern.</span><span class="sxs-lookup"><span data-stu-id="175f9-259">If you are running SQL Server 2005, you must modify the configuration of the service's connection string.</span></span> <span data-ttu-id="175f9-260">Wenn Sie das Beispiel computerübergreifend ausführen, ist SQL Server nur auf dem Servercomputer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="175f9-260">When running cross-machine, SQL Server is only required on the server machine.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="175f9-261">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="175f9-261">The samples may already be installed on your machine.</span></span> <span data-ttu-id="175f9-262">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="175f9-262">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="175f9-263">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="175f9-263">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="175f9-264">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="175f9-264">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
