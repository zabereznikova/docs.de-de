---
title: Beispiel zu stark typisierten Erweiterungen
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: 8dc6bca87989b1ee8e1ee440b0d64e2c196cc28f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978239"
---
# <a name="strongly-typed-extensions-sample"></a><span data-ttu-id="b8f9c-102">Beispiel zu stark typisierten Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="b8f9c-102">Strongly-Typed Extensions Sample</span></span>
<span data-ttu-id="b8f9c-103">Für das Beispiel wird die <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-103">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="b8f9c-104">Die in diesem Beispiel gezeigten Muster können jedoch in allen Syndication-Klassen verwendet werden, die Erweiterungsdaten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-104">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data.</span></span>  
  
 <span data-ttu-id="b8f9c-105">Das Syndication-Objektmodell (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> und verwandte Klassen) unterstützt lose typisierten Zugriff auf Erweiterungsdaten mithilfe der <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>-Eigenschaft und der <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-105">The Syndication object model (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, and related classes) supports loosely-typed access to extension data by using the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> properties.</span></span> <span data-ttu-id="b8f9c-106">In diesem Beispiel wird das Bereitstellen eines stark typisierten Zugriffs auf Erweiterungsdaten veranschaulicht, indem benutzerdefinierte, von <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> abgeleitete Klassen implementiert werden, die bestimmte anwendungsspezifische Erweiterungen als stark typisierte Eigenschaften verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-106">This sample shows how to provide strongly-typed access to extension data by implementing custom derived classes of <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> that make available certain application-specific extensions as strongly-typed properties.</span></span>  
  
 <span data-ttu-id="b8f9c-107">Außerdem wird als Beispiel veranschaulicht, wie ein im vorgeschlagenen RFC zu Atom-Threading-Erweiterungen definiertes Erweiterungselement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-107">As an example, this sample shows how to implement an extension element defined in the proposed Atom Threading Extensions RFC.</span></span> <span data-ttu-id="b8f9c-108">Dies dient nur zur Veranschaulichung. Das Beispiel ist keine vollständige Implementierung der vorgeschlagenen Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-108">This is for demonstration purposes only and this sample is not intended to be a full implementation of the proposed specification.</span></span>  
  
## <a name="sample-xml"></a><span data-ttu-id="b8f9c-109">Beispiel-XML</span><span class="sxs-lookup"><span data-stu-id="b8f9c-109">Sample XML</span></span>  
 <span data-ttu-id="b8f9c-110">Das folgende XML-Beispiel zeigt einen Atom 1.0-Eintrag mit einem zusätzlichen `<in-reply-to>`-Erweiterungselement.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-110">The following XML example shows an Atom 1.0 entry with an additional `<in-reply-to>` extension element.</span></span>  
  
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
  
 <span data-ttu-id="b8f9c-111">Das `<in-reply-to>`-Element gibt drei erforderliche Attribute an (`ref`, `type` und `href`), während gleichzeitig zusätzliche Erweiterungs Attribute und Erweiterungs Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-111">The `<in-reply-to>` element specifies three required attributes (`ref`, `type` and `href`) while also allowing for the presence of additional extension attributes and extension elements.</span></span>  
  
## <a name="modeling-the-in-reply-to-element"></a><span data-ttu-id="b8f9c-112">Modellieren des In-Reply-To-Elements</span><span class="sxs-lookup"><span data-stu-id="b8f9c-112">Modeling the In-Reply-To element</span></span>  
 <span data-ttu-id="b8f9c-113">In diesem Beispiel wird das `<in-reply-to>`-Element als CLR modelliert, das <xref:System.Xml.Serialization.IXmlSerializable> implementiert. Dabei wird die Verwendung mit <xref:System.Runtime.Serialization.DataContractSerializer> ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-113">In this sample, the `<in-reply-to>` element is modeled as CLR that implements <xref:System.Xml.Serialization.IXmlSerializable>, which enables its use with the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="b8f9c-114">Außerdem werden einige Methoden und Eigenschaften für den Zugriff auf die Daten des Elements implementiert, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-114">It also implements some methods and properties for accessing the element’s data, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="b8f9c-115">Die `InReplyToElement`-Klasse implementiert Eigenschaften für das erforderliche Attribut (`HRef`, `MediaType` und `Source`) sowie Auflistungen für <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> und <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-115">The `InReplyToElement` class implements properties for the required attribute (`HRef`, `MediaType`, and `Source`) as well as collections to hold <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span></span>  
  
 <span data-ttu-id="b8f9c-116">Die `InReplyToElement`-Klasse implementiert die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle, mit der direkt gesteuert werden kann, wie Objektinstanzen aus XML gelesen und in XML geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-116">The `InReplyToElement` class implements the <xref:System.Xml.Serialization.IXmlSerializable> interface, which allows direct control over how object instances are read from and written to XML.</span></span> <span data-ttu-id="b8f9c-117">Die `ReadXml`-Methode liest zuerst Werte für die Eigenschaften `Ref`, `HRef`, `Source` und `MediaType` aus dem übergebenen <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-117">The `ReadXml` method first reads the values for the `Ref`, `HRef`, `Source`, and `MediaType` properties from the <xref:System.Xml.XmlReader> passed to it.</span></span> <span data-ttu-id="b8f9c-118">Alle unbekannten Attribute werden in der <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>-Auflistung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-118">Any unknown attributes are stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection.</span></span> <span data-ttu-id="b8f9c-119">Wenn alle Attribute gelesen wurden, wird <xref:System.Xml.XmlReader.ReadStartElement> aufgerufen, um den Reader an das nächste Element weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-119">When all the attributes have been read, <xref:System.Xml.XmlReader.ReadStartElement> is called to advance the reader to the next element.</span></span> <span data-ttu-id="b8f9c-120">Da das von dieser Klasse modellierte Element keine erforderlichen untergeordneten Elemente aufweist, werden untergeordnete Elemente in `XElement`-Instanzen gepuffert und in der <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>-Auflistung gespeichert, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-120">Because the element modeled by this class has no required children, the child elements get buffered into `XElement` instances and stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="b8f9c-121">In `WriteXml` schreibt die `InReplyToElement`-Methode zuerst die Werte der Eigenschaften `Ref`, `HRef`, `Source` und `MediaType` als XML-Attribute (`WriteXml` ist nicht zuständig für das Schreiben des tatsächlichen äußeren Elements wie beim Aufrufer von `WriteXml`).</span><span class="sxs-lookup"><span data-stu-id="b8f9c-121">In `WriteXml`, the `InReplyToElement` method first writes out the values of the `Ref`, `HRef`, `Source`, and `MediaType` properties as XML attributes (`WriteXml` is not responsible for writing the actual outer element itself, as that done by the caller of `WriteXml`).</span></span> <span data-ttu-id="b8f9c-122">Außerdem wird auch der Inhalt von <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> und <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> an den Writer geschrieben, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-122">It also writes the contents of the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> to the writer, as shown in the following code.</span></span>  
  
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
  
## <a name="threadedfeed-and-threadeditem"></a><span data-ttu-id="b8f9c-123">ThreadedFeed und ThreadedItem</span><span class="sxs-lookup"><span data-stu-id="b8f9c-123">ThreadedFeed and ThreadedItem</span></span>  
 <span data-ttu-id="b8f9c-124">Im Beispiel werden `SyndicationItems` mit `InReplyTo`-Erweiterungen von der `ThreadedItem`-Klasse modelliert.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-124">In the sample, `SyndicationItems` with `InReplyTo` extensions are modeled by the `ThreadedItem` class.</span></span> <span data-ttu-id="b8f9c-125">Entsprechend handelt es sich bei der `ThreadedFeed`-Klasse um einen `SyndicationFeed`, dessen Elemente Instanzen von `ThreadedItem` sind.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-125">Similarly, the `ThreadedFeed` class is a `SyndicationFeed` whose items are all instances of `ThreadedItem`.</span></span>  
  
 <span data-ttu-id="b8f9c-126">Die `ThreadedFeed`-Klasse erbt von `SyndicationFeed` und überschreibt `OnCreateItem`, um ein `ThreadedItem` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-126">The `ThreadedFeed` class inherits from `SyndicationFeed` and overrides `OnCreateItem` to return a `ThreadedItem`.</span></span> <span data-ttu-id="b8f9c-127">Außerdem wird eine Methode zum Zugriff auf die `Items`-Auflistung als `ThreadedItems` implementiert, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-127">It also implements a method for accessing the `Items` collection as `ThreadedItems`, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="b8f9c-128">Die Klasse `ThreadedItem` erbt von `SyndicationItem` und legt `InReplyToElement` als stark typisierte Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-128">The class `ThreadedItem` inherits from `SyndicationItem` and makes `InReplyToElement` as a strongly-typed property.</span></span> <span data-ttu-id="b8f9c-129">So kann bequem programmgesteuert auf die `InReplyTo`-Erweiterungsdaten zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-129">This provides for convenient programmatic access to the `InReplyTo` extension data.</span></span> <span data-ttu-id="b8f9c-130">Außerdem werden `TryParseElement` und `WriteElementExtensions` für das Lesen und Schreiben der Erweiterungsdaten implementiert, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-130">It also implements `TryParseElement` and `WriteElementExtensions` for reading and writing its extension data, as shown in the following code.</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b8f9c-131">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="b8f9c-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b8f9c-132">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b8f9c-133">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b8f9c-134">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b8f9c-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b8f9c-135">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b8f9c-136">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-136">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="b8f9c-137">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8f9c-138">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b8f9c-138">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
