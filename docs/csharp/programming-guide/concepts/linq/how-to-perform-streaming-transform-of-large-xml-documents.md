---
title: 'Vorgehensweise: Durchführen einer Streamingtransformation großer XML-Dokumente (C#)'
ms.date: 07/20/2015
ms.assetid: 5f16d1f8-5370-4b55-b0c8-e497df163037
ms.openlocfilehash: 9eb2e832f798e550ef3b534b0c9a0e3416378b43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169103"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-c"></a><span data-ttu-id="e18fa-102">Vorgehensweise: Durchführen einer Streamingtransformation großer XML-Dokumente (C#)</span><span class="sxs-lookup"><span data-stu-id="e18fa-102">How to perform streaming transform of large XML documents (C#)</span></span>
<span data-ttu-id="e18fa-103">Es kann vorkommen, dass Sie große XML-Dateien transformieren und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist.</span><span class="sxs-lookup"><span data-stu-id="e18fa-103">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="e18fa-104">Wenn Sie versuchen, eine XML-Struktur mit einer sehr großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv.</span><span class="sxs-lookup"><span data-stu-id="e18fa-104">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="e18fa-105">Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="e18fa-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="e18fa-106">Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten.</span><span class="sxs-lookup"><span data-stu-id="e18fa-106">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="e18fa-107">Einige Standardabfrageoperatoren, wie <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, sortieren sie und geben dann das erste Element in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="e18fa-107">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="e18fa-108">Beachten Sie, dass Sie bei der Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, keine minimale Speicherbeanspruchung für Ihre Anwendung aufrechterhalten können.</span><span class="sxs-lookup"><span data-stu-id="e18fa-108">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
<span data-ttu-id="e18fa-109">Aber selbst dann, wenn Sie das in [Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) beschriebene Verfahren verwenden, wird die Speicherbeanspruchung zu groß, wenn Sie versuchen, eine XML-Struktur unter Einbeziehung des transformierten Dokuments zusammenzustellen.</span><span class="sxs-lookup"><span data-stu-id="e18fa-109">Even if you use the technique described in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>
  
 <span data-ttu-id="e18fa-110">Es gibt im Wesentlichen zwei Lösungsansätze:</span><span class="sxs-lookup"><span data-stu-id="e18fa-110">There are two main approaches.</span></span> <span data-ttu-id="e18fa-111">Zum einen können Sie versuchen, sich die verzögerte Verarbeitung von <xref:System.Xml.Linq.XStreamingElement> zunutze zu machen,</span><span class="sxs-lookup"><span data-stu-id="e18fa-111">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="e18fa-112">und zum anderen können Sie einen <xref:System.Xml.XmlWriter> erstellen und dann mithilfe von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Elemente in den <xref:System.Xml.XmlWriter> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e18fa-112">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="e18fa-113">In diesem Thema werden beide Ansätze besprochen.</span><span class="sxs-lookup"><span data-stu-id="e18fa-113">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e18fa-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e18fa-114">Example</span></span>  
 <span data-ttu-id="e18fa-115">Das folgende Beispiel baut auf dem Beispiel in [Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) auf.</span><span class="sxs-lookup"><span data-stu-id="e18fa-115">The following example builds on the example in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>
  
 <span data-ttu-id="e18fa-116">In diesem Beispiel wird die verzögerte Ausführung von <xref:System.Xml.Linq.XStreamingElement> verwendet, um die Ausgabe zu streamen.</span><span class="sxs-lookup"><span data-stu-id="e18fa-116">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="e18fa-117">Damit kann auch ein sehr großes Dokument transformiert werden, ohne dass die Speicherbeanspruchung zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="e18fa-117">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="e18fa-118">Beachten Sie, dass die benutzerdefinierte Achse (`StreamCustomerItem`) so geschrieben ist, dass sie über ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen verfügt. Diese Elemente werden wie im folgenden Source.xml-Dokument angeordnet.</span><span class="sxs-lookup"><span data-stu-id="e18fa-118">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="e18fa-119">Eine robustere Implementierung würde jedoch darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.</span><span class="sxs-lookup"><span data-stu-id="e18fa-119">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="e18fa-120">Das Quelldokument (<legacyBold>Source.xml</legacyBold>) sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e18fa-120">The following is the source document, Source.xml:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null)  
                        {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XStreamingElement root = new XStreamingElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    root.Save("Test.xml");  
    Console.WriteLine(File.ReadAllText("Test.xml"));  
}  
```  
  
 <span data-ttu-id="e18fa-121">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e18fa-121">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="e18fa-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e18fa-122">Example</span></span>  
<span data-ttu-id="e18fa-123">Das folgende Beispiel baut ebenfalls auf dem Beispiel in [Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) auf.</span><span class="sxs-lookup"><span data-stu-id="e18fa-123">The following example also builds on the example in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>
  
 <span data-ttu-id="e18fa-124">In diesem Beispiel wird die Fähigkeit von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] genutzt, Elemente in einen <xref:System.Xml.XmlWriter> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e18fa-124">This example uses the capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="e18fa-125">Damit kann auch ein sehr großes Dokument transformiert werden, ohne dass die Speicherbeanspruchung zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="e18fa-125">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="e18fa-126">Beachten Sie, dass die benutzerdefinierte Achse (`StreamCustomerItem`) so geschrieben ist, dass sie über ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen verfügt. Diese Elemente werden wie im folgenden Source.xml-Dokument angeordnet.</span><span class="sxs-lookup"><span data-stu-id="e18fa-126">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="e18fa-127">Eine robustere Implementierung würde jedoch entweder das Quelldokument mit einer XSD prüfen oder darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.</span><span class="sxs-lookup"><span data-stu-id="e18fa-127">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="e18fa-128">In diesem Beispiel wird das gleiche Quelldokument (<legacyBold>Source.xml</legacyBold>) wie im Beispiel oben verwendet.</span><span class="sxs-lookup"><span data-stu-id="e18fa-128">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="e18fa-129">Es erzeugt auch genau die gleiche Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e18fa-129">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="e18fa-130">Für das Streamen der XML-Ausgabe wird empfohlen, nicht in einen <xref:System.Xml.Linq.XStreamingElement> zu schreiben, sondern <xref:System.Xml.XmlWriter> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e18fa-130">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    IEnumerable<XElement> srcTree =  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        );  
    XmlWriterSettings xws = new XmlWriterSettings();  
    xws.OmitXmlDeclaration = true;  
    xws.Indent = true;  
    using (XmlWriter xw = XmlWriter.Create("Output.xml", xws)) {  
        xw.WriteStartElement("Root");  
        foreach (XElement el in srcTree)  
            el.WriteTo(xw);  
        xw.WriteEndElement();  
    }  
  
    string str = File.ReadAllText("Output.xml");  
    Console.WriteLine(str);  
}  
```  
  
 <span data-ttu-id="e18fa-131">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e18fa-131">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  