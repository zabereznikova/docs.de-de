---
title: 'Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)'
description: Erfahren Sie, wie Sie XML-Fragmente mit Zugriff auf Headerinformationen streamen. Mit Streamingverfahren lässt sich eine übermäßige Speicherauslastung vermeiden.
ms.date: 07/20/2015
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: 8bfded96ea1fa6b096d56ae0736002b9062d58b6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303217"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a><span data-ttu-id="cd2d9-104">Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="cd2d9-104">How to stream XML fragments with access to header information (C#)</span></span>
<span data-ttu-id="cd2d9-105">Es kann vorkommen, dass Sie willkürlich große XML-Dateien lesen und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-105">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="cd2d9-106">Wenn Sie versuchen, eine XML-Struktur mit einer großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-106">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="cd2d9-107">Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-107">Therefore, you should use a streaming technique instead.</span></span>  
  
<span data-ttu-id="cd2d9-108">Zu diesem Zweck können Sie die Anwendung mit <xref:System.Xml.XmlReader> schreiben.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-108">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="cd2d9-109">Es empfiehlt sich aber häufig, zum Abfragen der XML-Struktur LINQ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-109">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="cd2d9-110">Bei Verwendung von  können Sie eine eigene benutzerdefinierte Achsenmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-110">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="cd2d9-111">Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben einer LINQ to XML-Axis-Methode (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="cd2d9-111">For more information, see [How to write a LINQ to XML axis method (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span></span>
  
 <span data-ttu-id="cd2d9-112">Zum Schreiben einer eigenen Achsenmethode müssen Sie zunächst eine kleine Methode schreiben, die mit dem <xref:System.Xml.XmlReader> Knoten so lange liest, bis sie zu einem der Knoten gelangt, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-112">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="cd2d9-113">Die Methode ruft dann die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode auf, die aus dem <xref:System.Xml.XmlReader> liest und ein XML-Fragment instanziiert.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-113">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="cd2d9-114">Daraufhin wird jedes Fragment mit `yield return` an die Methode zurückgegeben, die Ihre benutzerdefinierte Achsenmethode aufzählt.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-114">It then yields each fragment through `yield return` to the method that is enumerating your custom axis method.</span></span> <span data-ttu-id="cd2d9-115">Sie können dann LINQ-Abfragen für die benutzerdefinierte Achsenmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-115">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="cd2d9-116">Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-116">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="cd2d9-117">Einige Standardabfrageoperatoren, wie <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, sortieren sie und geben dann das erste Element in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-117">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="cd2d9-118">Bei Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, erhalten Sie keinen kleinen Arbeitsspeicher-Fußabdruck.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-118">If you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd2d9-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd2d9-119">Example</span></span>  

<span data-ttu-id="cd2d9-120">Manchmal wird das Problem noch ein wenig interessanter.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-120">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="cd2d9-121">Im folgenden XML-Dokument muss der Benutzer Ihrer benutzerdefinierten Achsenmethode auch die Namen der Kunden kennen, zu denen die einzelnen Elemente gehören.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-121">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
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
  
 <span data-ttu-id="cd2d9-122">Dieses Beispiel sucht auch nach diesen Headerinformationen, speichert sie und konstruiert dann eine kleine XML-Struktur, die sowohl die Headerinformationen als auch die Detailinformationen enthält, die von Ihnen aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-122">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="cd2d9-123">Die Achsenmethode gibt daraufhin diese neue, kleine XML-Struktur zurück.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-123">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="cd2d9-124">Die Abfrage verfügt damit sowohl über Zugriff auf die Headerinformationen als auch über Zugriff auf die Detailinformationen.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-124">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="cd2d9-125">Dieser Ansatz führt zu einer geringen Speicherbeanspruchung.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-125">This approach has a small memory footprint.</span></span> <span data-ttu-id="cd2d9-126">Da jedes XML-Detailfragment zurückgegeben wird, bleiben keine Verweise auf vorherige Fragmente erhalten. Es steht damit für die Garbage Collection (automatische Speicherbereinigung) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-126">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="cd2d9-127">Bei diesem Verfahren werden viele kurzlebige Objekte auf dem Heap erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-127">This technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="cd2d9-128">Im folgenden Beispiel wird die Vorgehensweise bei der Implementierung und Verwendung einer benutzerdefinierten Achsenmethode gezeigt, die XML-Fragmente aus der durch den URI angegebenen Datei streamt.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-128">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="cd2d9-129">Diese benutzerdefinierte Achse ist so geschrieben, dass sie ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen erwartet. Diese Elemente werden wie im Dokument `Source.xml` oben angeordnet.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-129">This custom axis is written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="cd2d9-130">Dabei handelt es sich um eine eher einfache Implementierung.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-130">It is a simplistic implementation.</span></span> <span data-ttu-id="cd2d9-131">Eine robustere Implementierung würde darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.</span><span class="sxs-lookup"><span data-stu-id="cd2d9-131">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
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
    XElement xmlTree = new XElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    Console.WriteLine(xmlTree);  
}  
```  
  
 <span data-ttu-id="cd2d9-132">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cd2d9-132">This code produces the following output:</span></span>  
  
```xml  
<Root>  
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
</Root>  
```  
