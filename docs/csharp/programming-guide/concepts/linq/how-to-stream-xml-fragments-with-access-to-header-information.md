---
title: 'Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 07fe45bb54c0d8b867cd3ae03fc3ed940243a538
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a><span data-ttu-id="3cf29-102">Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="3cf29-102">How to: Stream XML Fragments with Access to Header Information (C#)</span></span>
<span data-ttu-id="3cf29-103">Es kann vorkommen, dass Sie willkürlich große XML-Dateien lesen und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist.</span><span class="sxs-lookup"><span data-stu-id="3cf29-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="3cf29-104">Wenn Sie versuchen, eine XML-Struktur mit einer großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv.</span><span class="sxs-lookup"><span data-stu-id="3cf29-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="3cf29-105">Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cf29-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="3cf29-106">Zu diesem Zweck können Sie die Anwendung mit <xref:System.Xml.XmlReader> schreiben.</span><span class="sxs-lookup"><span data-stu-id="3cf29-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="3cf29-107">Es empfiehlt sich aber häufig, zum Abfragen der XML-Struktur [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cf29-107">However, you might want to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to query the XML tree.</span></span> <span data-ttu-id="3cf29-108">Bei Verwendung von  können Sie eine eigene benutzerdefinierte Achsenmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="3cf29-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="3cf29-109">Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben einer LINQ to XML-Axis-Methode (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="3cf29-109">For more information, see [How to: Write a LINQ to XML Axis Method (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).</span></span>  
  
 <span data-ttu-id="3cf29-110">Zum Schreiben einer eigenen Achsenmethode müssen Sie zunächst eine kleine Methode schreiben, die mit dem <xref:System.Xml.XmlReader> Knoten so lange liest, bis sie zu einem der Knoten gelangt, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="3cf29-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="3cf29-111">Die Methode ruft dann die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode auf, die aus dem <xref:System.Xml.XmlReader> liest und ein XML-Fragment instanziiert.</span><span class="sxs-lookup"><span data-stu-id="3cf29-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="3cf29-112">Daraufhin wird jedes Fragment mit `yield return` an die Methode zurückgegeben, die Ihre benutzerdefinierte Achsenmethode aufzählt.</span><span class="sxs-lookup"><span data-stu-id="3cf29-112">It then yields each fragment through `yield return` to the method that is enumerating your custom axis method.</span></span> <span data-ttu-id="3cf29-113">Sie können dann LINQ-Abfragen für die benutzerdefinierte Achsenmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="3cf29-113">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="3cf29-114">Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten.</span><span class="sxs-lookup"><span data-stu-id="3cf29-114">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="3cf29-115">Einige Standardabfrageoperatoren, wie <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, sortieren sie und geben dann das erste Element in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="3cf29-115">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="3cf29-116">Beachten Sie, dass Sie bei der Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, keine minimale Speicherbeanspruchung aufrechterhalten können.</span><span class="sxs-lookup"><span data-stu-id="3cf29-116">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cf29-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cf29-117">Example</span></span>  
 <span data-ttu-id="3cf29-118">Manchmal wird das Problem noch ein wenig interessanter.</span><span class="sxs-lookup"><span data-stu-id="3cf29-118">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="3cf29-119">Im folgenden XML-Dokument muss der Benutzer Ihrer benutzerdefinierten Achsenmethode auch die Namen der Kunden kennen, zu denen die einzelnen Elemente gehören.</span><span class="sxs-lookup"><span data-stu-id="3cf29-119">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
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
  
 <span data-ttu-id="3cf29-120">Dieses Beispiel sucht auch nach diesen Headerinformationen, speichert sie und konstruiert dann eine kleine XML-Struktur, die sowohl die Headerinformationen als auch die Detailinformationen enthält, die von Ihnen aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="3cf29-120">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="3cf29-121">Die Achsenmethode gibt daraufhin diese neue, kleine XML-Struktur zurück.</span><span class="sxs-lookup"><span data-stu-id="3cf29-121">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="3cf29-122">Die Abfrage verfügt damit sowohl über Zugriff auf die Headerinformationen als auch über Zugriff auf die Detailinformationen.</span><span class="sxs-lookup"><span data-stu-id="3cf29-122">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="3cf29-123">Dieser Ansatz führt zu einer geringen Speicherbeanspruchung.</span><span class="sxs-lookup"><span data-stu-id="3cf29-123">This approach has a small memory footprint.</span></span> <span data-ttu-id="3cf29-124">Da jedes XML-Detailfragment zurückgegeben wird, bleiben keine Verweise auf vorherige Fragmente erhalten. Es steht damit für die Garbage Collection (automatische Speicherbereinigung) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3cf29-124">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="3cf29-125">Beachten Sie, dass bei diesem Verfahren viele kurzlebige Objekte auf dem Heap erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3cf29-125">Note that this technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="3cf29-126">Im folgenden Beispiel wird die Vorgehensweise bei der Implementierung und Verwendung einer benutzerdefinierten Achsenmethode gezeigt, die XML-Fragmente aus der durch den URI angegebenen Datei streamt.</span><span class="sxs-lookup"><span data-stu-id="3cf29-126">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="3cf29-127">Diese benutzerdefinierte Achse ist so geschrieben, dass sie ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen erwartet. Diese Elemente werden wie im Dokument `Source.xml` oben angeordnet.</span><span class="sxs-lookup"><span data-stu-id="3cf29-127">This custom axis is specifically written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="3cf29-128">Dabei handelt es sich um eine eher einfache Implementierung.</span><span class="sxs-lookup"><span data-stu-id="3cf29-128">It is a simplistic implementation.</span></span> <span data-ttu-id="3cf29-129">Eine robustere Implementierung würde darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.</span><span class="sxs-lookup"><span data-stu-id="3cf29-129">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
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
  
 <span data-ttu-id="3cf29-130">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf29-130">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3cf29-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cf29-131">See Also</span></span>  
 [<span data-ttu-id="3cf29-132">Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="3cf29-132">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
