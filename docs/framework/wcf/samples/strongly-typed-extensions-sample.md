---
title: Beispiel für stark typisierte Erweiterungen
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: e5b74188d4c9c333858c60ff95a2a90b0e2e9418
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275930"
---
# <a name="strongly-typed-extensions-sample"></a>Beispiel für stark typisierte Erweiterungen

Für das Beispiel wird die <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse verwendet. Die in diesem Beispiel gezeigten Muster können jedoch in allen Syndication-Klassen verwendet werden, die Erweiterungsdaten unterstützen.  
  
 Das Syndication-Objektmodell (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> und verwandte Klassen) unterstützt lose typisierten Zugriff auf Erweiterungsdaten mithilfe der <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>-Eigenschaft und der <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>-Eigenschaft. Dieses Beispiel zeigt, wie Sie stark typisierten Zugriff auf Erweiterungs Daten bereitstellen, indem Sie benutzerdefinierte abgeleitete Klassen von implementieren <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> bestimmte anwendungsspezifische Erweiterungen als stark typisierte Eigenschaften verfügbar machen.  
  
 Außerdem wird als Beispiel veranschaulicht, wie ein im vorgeschlagenen RFC zu Atom-Threading-Erweiterungen definiertes Erweiterungselement definiert wird. Dies dient nur zur Veranschaulichung. Das Beispiel ist keine vollständige Implementierung der vorgeschlagenen Spezifikation.  
  
## <a name="sample-xml"></a>Beispiel-XML  

 Das folgende XML-Beispiel zeigt einen Atom 1.0-Eintrag mit einem zusätzlichen `<in-reply-to>`-Erweiterungselement.  
  
```xml  
<entry>  
    <id>tag:example.org,2005:1,2</id>  
    <title type="text">Another response to the original</title>  
    <summary type="text">  
         This is a response to the original entry</summary>  
    <updated>2006-03-01T12:12:13Z</updated>  
    <link href="http://www.example.org/entries/1/2" />  
    <in-reply-to p3:ref="tag:example.org,2005:1"
                 p3:href="http://www.example.org/entries/1"
                 p3:type="application/xhtml+xml"
                 xmlns:p3="http://contoso.org/syndication/thread/1.0"
                 xmlns="http://contoso.org/syndication/thread/1.0">  
      <anotherElement xmlns="http://www.w3.org/2005/Atom">  
                     Some more data</anotherElement>  
      <aDifferentElement xmlns="http://www.w3.org/2005/Atom">  
                     Even more data</aDifferentElement>  
    </in-reply-to>  
</entry>  
```  
  
 Das `<in-reply-to>` -Element gibt drei erforderliche Attribute `ref` an (, `type` und `href` ), während gleichzeitig zusätzliche Erweiterungs Attribute und Erweiterungs Elemente vorhanden sind.  
  
## <a name="modeling-the-in-reply-to-element"></a>Modellieren des In-Reply-To-Elements  

 In diesem Beispiel wird das `<in-reply-to>`-Element als CLR modelliert, das <xref:System.Xml.Serialization.IXmlSerializable> implementiert. Dabei wird die Verwendung mit <xref:System.Runtime.Serialization.DataContractSerializer> ermöglicht. Außerdem werden einige Methoden und Eigenschaften für den Zugriff auf die Daten des Elements implementiert, wie im folgenden Beispielcode gezeigt.  
  
```csharp  
[XmlRoot(ElementName = "in-reply-to", Namespace = "http://contoso.org/syndication/thread/1.0")]  
public class InReplyToElement : IXmlSerializable  
{  
    internal const string ElementName = "in-reply-to";  
    internal const string NsUri =
                  "http://contoso.org/syndication/thread/1.0";  
    private Dictionary<XmlQualifiedName, string> extensionAttributes;  
    private Collection<XElement> extensionElements;  
  
    public InReplyToElement()  
    {  
        this.extensionElements = new Collection<XElement>();  
        this.extensionAttributes = new Dictionary<XmlQualifiedName,
                                                          string>();  
    }  
  
    public Dictionary<XmlQualifiedName, string> AttributeExtensions  
    {  
        get { return this.extensionAttributes; }  
    }  
  
    public Collection<XElement> ElementExtensions  
    {  
        get { return this.extensionElements; }  
    }  
  
    public Uri Href  
    { get; set; }  
  
    public string MediaType  
    { get; set; }  
  
    public string Ref  
    { get; set; }  
  
    public Uri Source  
    { get; set; }  
}  
```  
  
 Die `InReplyToElement`-Klasse implementiert Eigenschaften für das erforderliche Attribut (`HRef`, `MediaType` und `Source`) sowie Auflistungen für <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> und <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.  
  
 Die `InReplyToElement`-Klasse implementiert die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle, mit der direkt gesteuert werden kann, wie Objektinstanzen aus XML gelesen und in XML geschrieben werden. Die `ReadXml`-Methode liest zuerst Werte für die Eigenschaften `Ref`, `HRef`, `Source` und `MediaType` aus dem übergebenen <xref:System.Xml.XmlReader>. Alle unbekannten Attribute werden in der <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>-Auflistung gespeichert. Wenn alle Attribute gelesen wurden, wird <xref:System.Xml.XmlReader.ReadStartElement> aufgerufen, um den Reader an das nächste Element weiterzugeben. Da das von dieser Klasse modellierte Element keine erforderlichen untergeordneten Elemente aufweist, werden untergeordnete Elemente in `XElement`-Instanzen gepuffert und in der <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>-Auflistung gespeichert, wie im folgenden Code dargestellt.  
  
```csharp
public void ReadXml(System.Xml.XmlReader reader)  
{  
    bool isEmpty = reader.IsEmptyElement;  
  
    if (reader.HasAttributes)  
    {  
        for (int i = 0; i < reader.AttributeCount; i++)  
        {  
            reader.MoveToNextAttribute();  
  
            if (reader.NamespaceURI == "")  
            {  
                if (reader.LocalName == "ref")  
                {  
                    this.Ref = reader.Value;  
                }  
                else if (reader.LocalName == "href")  
                {  
                    this.Href = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "source")  
                {  
                    this.Source = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "type")  
                {  
                    this.MediaType = reader.Value;  
                }  
                else  
                {  
                    this.AttributeExtensions.Add(new
                                 XmlQualifiedName(reader.LocalName,
                                 reader.NamespaceURI),
                                 reader.Value);  
                }  
            }  
        }  
    }  
  
    reader.ReadStartElement();  
  
    if (!isEmpty)  
    {  
        while (reader.IsStartElement())  
        {  
            ElementExtensions.Add(  
                  (XElement) XElement.ReadFrom(reader));  
        }  
        reader.ReadEndElement();  
    }  
}  
```  
  
 In `WriteXml` schreibt die `InReplyToElement`-Methode zuerst die Werte der Eigenschaften `Ref`, `HRef`, `Source` und `MediaType` als XML-Attribute (`WriteXml` ist nicht zuständig für das Schreiben des tatsächlichen äußeren Elements wie beim Aufrufer von `WriteXml`). Außerdem wird auch der Inhalt von <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> und <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> an den Writer geschrieben, wie im folgenden Code dargestellt.  
  
```csharp
public void WriteXml(System.Xml.XmlWriter writer)  
{  
    if (this.Ref != null)  
    {  
        writer.WriteAttributeString("ref", InReplyToElement.NsUri,
                                            this.Ref);  
    }  
    if (this.Href != null)  
    {  
        writer.WriteAttributeString("href", InReplyToElement.NsUri,
                                                this.Href.ToString());  
    }  
    if (this.Source != null)  
    {  
        writer.WriteAttributeString("source", InReplyToElement.NsUri,
                                              this.Source.ToString());  
    }  
    if (this.MediaType != null)  
    {  
        writer.WriteAttributeString("type", InReplyToElement.NsUri,
                                                    this.MediaType);  
    }  
  
    foreach (KeyValuePair<XmlQualifiedName, string> kvp in
                                             this.AttributeExtensions)  
    {  
        writer.WriteAttributeString(kvp.Key.Name, kvp.Key.Namespace,
                                                   kvp.Value);  
    }  
  
    foreach (XElement element in this.ElementExtensions)  
    {  
        element.WriteTo(writer);  
    }  
}  
```  
  
## <a name="threadedfeed-and-threadeditem"></a>ThreadedFeed und ThreadedItem  

 Im Beispiel werden `SyndicationItems` mit `InReplyTo`-Erweiterungen von der `ThreadedItem`-Klasse modelliert. Entsprechend handelt es sich bei der `ThreadedFeed`-Klasse um einen `SyndicationFeed`, dessen Elemente Instanzen von `ThreadedItem` sind.  
  
 Die `ThreadedFeed`-Klasse erbt von `SyndicationFeed` und überschreibt `OnCreateItem`, um ein `ThreadedItem` zurückzugeben. Außerdem wird eine Methode zum Zugriff auf die `Items`-Auflistung als `ThreadedItems` implementiert, wie im folgenden Code dargestellt.  
  
```csharp
public class ThreadedFeed : SyndicationFeed  
{  
    public ThreadedFeed()  
    {  
    }  
  
    public IEnumerable<ThreadedItem> ThreadedItems  
    {  
        get  
        {  
            return this.Items.Cast<ThreadedItem>();  
        }  
    }  
  
    protected override SyndicationItem CreateItem()  
    {  
        return new ThreadedItem();  
    }  
}  
```  
  
 Die `ThreadedItem` -Klasse erbt von `SyndicationItem` und stellt `InReplyToElement` als stark typisierte Eigenschaft dar. So kann bequem programmgesteuert auf die `InReplyTo`-Erweiterungsdaten zugegriffen werden. Außerdem werden `TryParseElement` und `WriteElementExtensions` für das Lesen und Schreiben der Erweiterungsdaten implementiert, wie im folgenden Code dargestellt.  
  
```csharp
public class ThreadedItem : SyndicationItem  
{  
    private InReplyToElement inReplyTo;  
    // Constructors  
        public ThreadedItem()  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
        public ThreadedItem(string title, string content, Uri itemAlternateLink, string id, DateTimeOffset lastUpdatedTime) : base(title, content, itemAlternateLink, id, lastUpdatedTime)  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
    public InReplyToElement InReplyTo  
    {  
        get { return this.inReplyTo; }  
    }  
  
    protected override bool TryParseElement(  
                        System.Xml.XmlReader reader,
                        string version)  
    {  
        if (version == SyndicationVersions.Atom10 &&  
            reader.NamespaceURI == InReplyToElement.NsUri &&  
            reader.LocalName == InReplyToElement.ElementName)  
        {  
            this.inReplyTo = new InReplyToElement();  
  
            this.InReplyTo.ReadXml(reader);  
  
            return true;  
        }  
        else  
        {  
            return base.TryParseElement(reader, version);  
        }  
    }  
  
    protected override void WriteElementExtensions(XmlWriter writer,
                                                 string version)  
    {  
        if (this.InReplyTo != null &&
                     version == SyndicationVersions.Atom10)  
        {  
            writer.WriteStartElement(InReplyToElement.ElementName,
                                           InReplyToElement.NsUri);  
            this.InReplyTo.WriteXml(writer);  
            writer.WriteEndElement();  
        }  
  
        base.WriteElementExtensions(writer, version);  
    }  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
