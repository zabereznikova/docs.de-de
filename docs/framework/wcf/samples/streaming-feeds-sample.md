---
title: Beispiel zum Streaming von Feeds
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: ede1dbb4f5c682b8182dda4888a9cbd373b95dd8
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976375"
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="ae145-102">Beispiel zum Streaming von Feeds</span><span class="sxs-lookup"><span data-stu-id="ae145-102">Streaming Feeds Sample</span></span>
<span data-ttu-id="ae145-103">In diesem Beispiel wird veranschaulicht, wie Syndication-Feeds verwaltet werden, die eine große Anzahl von Elementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ae145-103">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="ae145-104">Auf dem Server zeigt das Beispiel, wie die Erstellung einzelner <xref:System.ServiceModel.Syndication.SyndicationItem>-Objekte innerhalb des Feeds bis unmittelbar vor den Zeitpunkt verzögert werden kann, zu dem das Element in den Netzwerkstream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ae145-104">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="ae145-105">Auf dem Client zeigt das Beispiel, wie mit einem benutzerdefinierten Syndication-Feed-Formatierungsprogramm einzelne Elemente aus dem Netzwerkstream gelesen werden können, sodass der Feed, aus dem gelesen wird, nie vollständig im Speicher gepuffert wird.</span><span class="sxs-lookup"><span data-stu-id="ae145-105">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="ae145-106">Um die Streamingfähigkeiten der Syndication-API am besten demonstrieren zu können, verwendet dieses Beispiel ein etwas unwahrscheinliches Szenario, in dem der Server einen Feed zugänglich macht, der eine unbegrenzte Anzahl von Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="ae145-106">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="ae145-107">In diesem Fall generiert der Server so lange neue Elemente und fügt sie in den Feed ein, bis er feststellt, dass der Client eine bestimmte Anzahl von Elementen (in der Standardeinstellung 10) aus dem Feed gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="ae145-107">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="ae145-108">Der Einfachheit halber werden sowohl der Client als auch der Server im gleichen Prozess implementiert und verfolgen mithilfe eines freigegebenen `ItemCounter`-Objekts, wie viele Elemente der Client produziert hat.</span><span class="sxs-lookup"><span data-stu-id="ae145-108">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="ae145-109">Der `ItemCounter`-Typ ist nur zu dem Zweck vorhanden, damit das Beispielszenario sauber beendet werden kann. Für das Muster, das hier demonstriert wird, ist dieses Element nicht von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="ae145-109">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="ae145-110">Die Demonstration nutzt visuelle C# Iteratoren (mit dem `yield return`-Schlüsselwort Konstrukt).</span><span class="sxs-lookup"><span data-stu-id="ae145-110">The demonstration makes use of Visual C# iterators (using the `yield return` keyword construct).</span></span> <span data-ttu-id="ae145-111">Weitere Informationen zu Iteratoren finden Sie im Thema "using Iterators" auf der MSDN-Website.</span><span class="sxs-lookup"><span data-stu-id="ae145-111">For more information about iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="ae145-112">Dienst</span><span class="sxs-lookup"><span data-stu-id="ae145-112">Service</span></span>  
 <span data-ttu-id="ae145-113">Der Dienst implementiert einen grundlegenden <xref:System.ServiceModel.Web.WebGetAttribute>-Vertrag, der aus einem Vorgang besteht, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae145-113">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```csharp  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="ae145-114">Diesen Vertrag implementiert der Dienst mittels einer `ItemGenerator`-Klasse zum Erstellen eines potentiell unendlichen Streams von <xref:System.ServiceModel.Syndication.SyndicationItem>-Instanzen mithilfe eines Iterators, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae145-114">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```csharp
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="ae145-115">Beim Erstellen des Feeds verwendet die Dienstimplementierung statt einer gepufferten Auflistung von Elementen die Ausgabe von `ItemGenerator.GenerateItems()`.</span><span class="sxs-lookup"><span data-stu-id="ae145-115">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```csharp
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="ae145-116">Infolgedessen wird der Elementstream nie vollständig im Arbeitsspeicher gepuffert.</span><span class="sxs-lookup"><span data-stu-id="ae145-116">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="ae145-117">Sie können dieses Verhalten beobachten, indem Sie in der `yield return`-Anweisung in der `ItemGenerator.GenerateItems()`-Methode einen Haltepunkt festlegen und feststellen, dass dieser Haltepunkt zum ersten Mal erreicht wird, nachdem der Dienst das Ergebnis der `StreamedFeed()`-Methode zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="ae145-117">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="ae145-118">Client</span><span class="sxs-lookup"><span data-stu-id="ae145-118">Client</span></span>  
 <span data-ttu-id="ae145-119">Der Client in diesem Beispiel verwendet eine benutzerdefinierte <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>-Implementierung, die die Materialisierung einzelner Elemente im Feed verzögert, anstatt sie im Arbeitsspeicher zu puffern.</span><span class="sxs-lookup"><span data-stu-id="ae145-119">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="ae145-120">Die benutzerdefinierte `StreamedAtom10FeedFormatter`-Instanz wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="ae145-120">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="ae145-121">Normalerweise wird bei einem Aufruf von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> die Steuerung erst dann zurückgegeben, wenn der gesamte Inhalt des Feeds aus dem Netzwerk gelesen und im Arbeitsspeicher gepuffert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae145-121">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="ae145-122">Allerdings setzt das `StreamedAtom10FeedFormatter`-Objekt <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> so außer Kraft, dass statt einer gepufferten Auflistung ein Iterator zurückgegeben wird, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae145-122">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```csharp  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="ae145-123">Demzufolge werden die einzelnen Elemente erst dann aus dem Netzwerk gelesen, wenn die Clientanwendung, die die Ergebnisse von `ReadItems()` durchläuft, bereit ist, sie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae145-123">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="ae145-124">Sie können dieses Verhalten beobachten, indem Sie einen Haltepunkt für die `yield return`-Anweisung in `StreamedAtom10FeedFormatter.DelayReadItems()` festlegen und bemerken, dass dieser Haltepunkt zum ersten Mal gefunden wird, nachdem der Aufruf von `ReadFrom()` abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ae145-124">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="ae145-125">Die folgenden Anweisungen zeigen, wie das Beispiel erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ae145-125">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="ae145-126">Obwohl der Server keine Elemente mehr generiert, nachdem der Client 10 Elemente gelesen hat, zeigt die Ausgabe, dass der Client bedeutend mehr als 10 Elemente liest.</span><span class="sxs-lookup"><span data-stu-id="ae145-126">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="ae145-127">Das liegt daran, dass die im Beispiel verwendete Netzwerkbindung Daten in Vier-Kilobyte-Segmenten übermittelt.</span><span class="sxs-lookup"><span data-stu-id="ae145-127">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="ae145-128">Daher empfängt der Client 4&#160;KB Elementdaten, bevor er die Gelegenheit hat, auch nur ein einziges Element zu lesen.</span><span class="sxs-lookup"><span data-stu-id="ae145-128">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="ae145-129">Dieses Verhalten ist normal (wenn gestreamte HTTP-Daten in Segmenten einer vernünftigen Größe gesendet werden, ist das Leistungsverhalten besser).</span><span class="sxs-lookup"><span data-stu-id="ae145-129">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ae145-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ae145-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ae145-131">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ae145-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ae145-132">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ae145-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ae145-133">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ae145-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ae145-134">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ae145-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ae145-135">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ae145-135">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="ae145-136">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ae145-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae145-137">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ae145-137">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="ae145-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae145-138">See also</span></span>

- [<span data-ttu-id="ae145-139">Eigenständiger Diagnosefeed</span><span class="sxs-lookup"><span data-stu-id="ae145-139">Stand-Alone Diagnostics Feed</span></span>](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)
