---
title: "Beispiel zum Streaming von Feeds | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Beispiel zum Streaming von Feeds
In diesem Beispiel wird veranschaulicht, wie Syndication\-Feeds verwaltet werden, die eine große Anzahl von Elementen enthalten.Auf dem Server zeigt das Beispiel, wie die Erstellung einzelner <xref:System.ServiceModel.Syndication.SyndicationItem>\-Objekte innerhalb des Feeds bis unmittelbar vor den Zeitpunkt verzögert werden kann, zu dem das Element in den Netzwerkstream geschrieben wird.  
  
 Auf dem Client zeigt das Beispiel, wie mit einem benutzerdefinierten Syndication\-Feed\-Formatierungsprogramm einzelne Elemente aus dem Netzwerkstream gelesen werden können, sodass der Feed, aus dem gelesen wird, nie vollständig im Speicher gepuffert wird.  
  
 Um die Streamingfähigkeiten der Syndication\-API am besten demonstrieren zu können, verwendet dieses Beispiel ein etwas unwahrscheinliches Szenario, in dem der Server einen Feed zugänglich macht, der eine unbegrenzte Anzahl von Elementen enthält.In diesem Fall generiert der Server so lange neue Elemente und fügt sie in den Feed ein, bis er feststellt, dass der Client eine bestimmte Anzahl von Elementen \(in der Standardeinstellung 10\) aus dem Feed gelesen hat.Der Einfachheit halber werden sowohl der Client als auch der Server im gleichen Prozess implementiert und verfolgen mithilfe eines freigegebenen `ItemCounter`\-Objekts, wie viele Elemente der Client produziert hat.Der `ItemCounter`\-Typ ist nur zu dem Zweck vorhanden, damit das Beispielszenario sauber beendet werden kann. Für das Muster, das hier demonstriert wird, ist dieses Element nicht von Bedeutung.  
  
 Bei der Demonstration werden [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\-Iteratoren \(mit dem Schlüsselwortkonstrukt `yield``return`,\) verwendet.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Iteratoren finden Sie im Thema "Verwenden von Iteratoren" auf MSDN.  
  
## Dienst  
 Der Dienst implementiert einen grundlegenden <xref:System.ServiceModel.Web.WebGetAttribute>\-Vertrag, der aus einem Vorgang besteht, wie im folgenden Code gezeigt.  
  
```  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
  
```  
  
 Diesen Vertrag implementiert der Dienst mittels einer `ItemGenerator`\-Klasse zum Erstellen eines potentiell unendlichen Streams von <xref:System.ServiceModel.Syndication.SyndicationItem>\-Instanzen mithilfe eines Iterators, wie im folgenden Code gezeigt.  
  
```  
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
  
 Beim Erstellen des Feeds verwendet die Dienstimplementierung statt einer gepufferten Auflistung von Elementen die Ausgabe von `ItemGenerator.GenerateItems()`.  
  
```  
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
  
 Infolgedessen wird der Elementstream nie vollständig im Arbeitsspeicher gepuffert.Sie können dieses Verhalten beobachten, indem Sie in der `yield``return`\-Anweisung in der `ItemGenerator.GenerateItems()`\-Methode einen Haltepunkt setzen. Sie werden dann sehen, dass dieser Haltepunkt zum ersten Mal erreicht wird, nachdem der Dienst das Ergebnis der `StreamedFeed()`\-Methode zurückgegeben hat.  
  
## Client  
 Der Client in diesem Beispiel verwendet eine benutzerdefinierte <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>\-Implementierung, die die Materialisierung einzelner Elemente im Feed verzögert, anstatt sie im Arbeitsspeicher zu puffern.Die benutzerdefinierte `StreamedAtom10FeedFormatter`\-Instanz wird wie folgt verwendet:  
  
```  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
  
```  
  
 Normalerweise wird bei einem Aufruf von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> die Steuerung erst dann zurückgegeben, wenn der gesamte Inhalt des Feeds aus dem Netzwerk gelesen und im Arbeitsspeicher gepuffert wurde.Allerdings setzt das `StreamedAtom10FeedFormatter`\-Objekt <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> so außer Kraft, dass statt einer gepufferten Auflistung ein Iterator zurückgegeben wird, wie im folgenden Code gezeigt.  
  
```  
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
  
 Demzufolge werden die einzelnen Elemente erst dann aus dem Netzwerk gelesen, wenn die Clientanwendung, die die Ergebnisse von `ReadItems()` durchläuft, bereit ist, sie zu verwenden.Sie können dieses Verhalten beobachten, indem Sie in der `yield``return`\-Anweisung in der `StreamedAtom10FeedFormatter.DelayReadItems()`\-Methode einen Haltepunkt setzen. Sie werden dann sehen, dass dieser Haltepunkt zum ersten Mal erreicht wird, nachdem der Aufruf der `ReadFrom()`\-Methode abgeschlossen ist.  
  
 Die folgenden Anweisungen zeigen, wie das Beispiel erstellt und ausgeführt wird.Obwohl der Server keine Elemente mehr generiert, nachdem der Client 10 Elemente gelesen hat, zeigt die Ausgabe, dass der Client bedeutend mehr als 10 Elemente liest.Das liegt daran, dass die im Beispiel verwendete Netzwerkbindung Daten in Vier\-Kilobyte\-Segmenten übermittelt.Daher empfängt der Client 4 KB Elementdaten, bevor er die Gelegenheit hat, auch nur ein einziges Element zu lesen.Dieses Verhalten ist normal \(wenn gestreamte HTTP\-Daten in Segmenten einer vernünftigen Größe gesendet werden, ist das Leistungsverhalten besser\).  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## Siehe auch  
 [Eigenständige Diagnose \(Feed\)](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)