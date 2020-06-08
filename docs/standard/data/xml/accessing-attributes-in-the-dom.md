---
title: Zugreifen auf die Attribute im DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
ms.openlocfilehash: a77780621032e2ce59b9db04a179c7086588219b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291642"
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="10d68-102">Zugreifen auf die Attribute im DOM</span><span class="sxs-lookup"><span data-stu-id="10d68-102">Accessing Attributes in the DOM</span></span>

<span data-ttu-id="10d68-103">Attribute sind Eigenschaften des Elements und keine untergeordneten Elemente des entsprechenden Elements.</span><span class="sxs-lookup"><span data-stu-id="10d68-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="10d68-104">Dies stellt aufgrund der Methoden zum Navigieren zwischen nebengeordneten, übergeordneten und untergeordneten Knoten des XML-Dokumentobjektmodells (DOM) eine wichtige Unterscheidung dar.</span><span class="sxs-lookup"><span data-stu-id="10d68-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="10d68-105">Die **PreviousSibling**- und die **NextSibling**-Methode werden beispielsweise nicht zum Wechseln von einem Element zu einem Attribut oder zwischen Attributen verwendet.</span><span class="sxs-lookup"><span data-stu-id="10d68-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="10d68-106">Stattdessen ist ein Attribut eine Eigenschaft eines Elements und gehört zu einem Element. Das Attribut verfügt über eine **OwnerElement**-Eigenschaft und nicht über eine **parentNode**-Eigenschaft. Außerdem besitzt es verschiedene Navigationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="10d68-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>

<span data-ttu-id="10d68-107">Wenn es sich bei dem aktuellen Knoten um ein Element handelt, verwenden Sie die **HasAttribute**-Methode, um zu prüfen, ob Attribute mit dem Element verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="10d68-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="10d68-108">Wenn bekannt ist, dass ein Element Attribute besitzt, bestehen mehrere Möglichkeiten, um auf die Attribute zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="10d68-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="10d68-109">Um ein einzelnes Attribut von einem Element abzufragen, können Sie die **GetAttribute**-Methode und die **GetAttributeNode**-Methode des **XmlElement** verwenden oder alle Attribute in einer Auflistung abrufen.</span><span class="sxs-lookup"><span data-stu-id="10d68-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="10d68-110">Es ist hilfreich, eine Auflistung abzurufen, wenn Sie die Auflistung durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="10d68-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="10d68-111">Wenn Sie alle Attribute des Elements benötigen, verwenden Sie die **Attributes**-Eigenschaft des Elements, um alle Attribute in einer Auflistung abzufragen.</span><span class="sxs-lookup"><span data-stu-id="10d68-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>

## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="10d68-112">Abfragen aller Attribute in einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="10d68-112">Retrieving All Attributes into a Collection</span></span>

<span data-ttu-id="10d68-113">Falls Sie alle Attribute eines Elementknotens in einer Auflistung benötigen, rufen Sie die **XmlElement.Attributes**-Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="10d68-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="10d68-114">Dadurch wird die **XmlAttributeCollection** abgerufen, die alle Attribute eines Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="10d68-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="10d68-115">Die **XmlAttributeCollection**-Klasse erbt von der **XmlNamedNode**-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="10d68-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="10d68-116">Deshalb zählen zu den in der Auflistung verfügbaren Methoden und Eigenschaften außer spezifischen Methoden und Eigenschaften der **XmlAttributeCollection**-Klasse (z.B. die **ItemOf**-Eigenschaft oder die **Append**-Methode) auch solche Methoden und Eigenschaften, die in einer benannten Knotenzuordnung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="10d68-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="10d68-117">Jeder Eintrag in der Attributauflistung stellt einen **XmlAttribute**-Knoten dar.</span><span class="sxs-lookup"><span data-stu-id="10d68-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="10d68-118">Um die Anzahl von Attributen in einem Element zu bestimmen, rufen Sie die **XmlAttributeCollection** ab, und verwenden Sie die **Count**-Eigenschaft, um anzuzeigen, wie viele **XmlAttribute**-Knoten die Auflistung enthält.</span><span class="sxs-lookup"><span data-stu-id="10d68-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>

<span data-ttu-id="10d68-119">Im folgenden Codebeispiel wird dargestellt, wie eine Attributauflistung mit der **Count**-Methode für den Schleifenindex durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="10d68-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="10d68-120">Im folgenden Code wird dargestellt, wie ein einzelnes Attribut aus einer Auflistung abgefragt und dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10d68-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim myElement As XmlElement = doc.DocumentElement

        ' Create an attribute collection from the element.
        Dim attrColl As XmlAttributeCollection = myElement.Attributes

        ' Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...")
        Dim i As Integer
        For i = 0 To attrColl.Count - 1
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)
            Console.Write("{0}", attrColl.ItemOf(i).Value)
            Console.WriteLine()
        Next

        ' Retrieve a single attribute from the collection; specifically, the
        ' attribute with the name "misc".
        Dim attr As XmlAttribute = attrColl("misc")

        ' Retrieve the value from that attribute.
        Dim miscValue As String = attr.InnerXml

        Console.WriteLine("Display the attribute information.")
        Console.WriteLine(miscValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{

    public static void Main()
    {
        XmlDocument doc = new XmlDocument();
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +
                      "<title>The Handmaid's Tale</title>" +
                      "<price>14.95</price>" +
                      "</book>");

        // Move to an element.
        XmlElement myElement = doc.DocumentElement;

        // Create an attribute collection from the element.
        XmlAttributeCollection attrColl = myElement.Attributes;

        // Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...");
        for (int i = 0; i < attrColl.Count; i++)
        {
            Console.Write("{0} = ", attrColl[i].Name);
            Console.Write("{0}", attrColl[i].Value);
            Console.WriteLine();
        }

        // Retrieve a single attribute from the collection; specifically, the
        // attribute with the name "misc".
        XmlAttribute attr = attrColl["misc"];

        // Retrieve the value from that attribute.
        String miscValue = attr.InnerXml;

        Console.WriteLine("Display the attribute information.");
        Console.WriteLine(miscValue);

    }
}
```

<span data-ttu-id="10d68-121">In diesem Beispiel wird die folgende Ausgabe dargestellt:</span><span class="sxs-lookup"><span data-stu-id="10d68-121">This example displays the following output:</span></span>

<span data-ttu-id="10d68-122">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="10d68-122">**Output**</span></span>

<span data-ttu-id="10d68-123">Alle Attribute in der Auflistung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="10d68-123">Display all the attributes in the collection.</span></span>

```console
genre = novel
ISBN = 1-861001-57-5
misc = sale item
Display the attribute information.
sale item
```

<span data-ttu-id="10d68-124">Die Informationen in einer Attributauflistung können nach Namen oder Indexnummer abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="10d68-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="10d68-125">Im oben aufgeführten Beispiel wird dargestellt, wie Daten nach Namen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="10d68-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="10d68-126">Im nächsten Beispiel wird dargestellt, wie Daten nach Indexnummer abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="10d68-126">The next example shows how to retrieve data by index number.</span></span>

<span data-ttu-id="10d68-127">Da es sich bei der **XmlAttributeCollection**-Klasse um eine Auflistung handelt, die nach Namen oder Index durchlaufen werden kann, wird in diesem Beispiel die Auswahl des ersten Attributs aus der Auflistung mit einem nullbasierten (0) Index dargestellt, wobei die Datei **baseuri.xml** als Eingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10d68-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>

### <a name="input"></a><span data-ttu-id="10d68-128">Eingabe</span><span class="sxs-lookup"><span data-stu-id="10d68-128">Input</span></span>

```xml
<!-- XML fragment -->
<book genre="novel">
  <title>Pride And Prejudice</title>
</book>
```

```vb
Option Explicit On
Option Strict On

Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()
        ' Create the XmlDocument.
        Dim doc As New XmlDocument()
        doc.Load("http://localhost/baseuri.xml")

        ' Display information on the attribute node. The value
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)
        Console.WriteLine("The value of the attribute:  {0}", attr.InnerText)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{
  public static void Main()
  {
    // Create the XmlDocument.
    XmlDocument doc = new XmlDocument();

    doc.Load("http://localhost/baseuri.xml");

    // Display information on the attribute node. The value
    // returned for BaseURI is 'http://localhost/baseuri.xml'.
    XmlAttribute attr = doc.DocumentElement.Attributes[0];
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);
    Console.WriteLine("The value of the attribute:  {0}", attr.InnerText);
  }
}
```

## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="10d68-129">Abrufen eines einzelnen Attributknotens</span><span class="sxs-lookup"><span data-stu-id="10d68-129">Retrieving an Individual Attribute Node</span></span>

<span data-ttu-id="10d68-130">Zum Abrufen eines einzelnen Attributknotens aus einem Element wird die <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="10d68-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="10d68-131">Sie gibt ein Objekt des Typs **XmlAttribute** zurück.</span><span class="sxs-lookup"><span data-stu-id="10d68-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="10d68-132">Wenn das **XmlAttribute**-Objekt vorhanden ist, sind alle Methoden und Eigenschaften, die in der <xref:System.Xml.XmlAttribute?displayProperty=nameWithType>-Klasse verfügbar sind, in diesem Objekt verfügbar, wie das Suchen nach dem **OwnerElement**.</span><span class="sxs-lookup"><span data-stu-id="10d68-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim root As XmlElement
        root = doc.DocumentElement

        ' Get an attribute.
        Dim attr As XmlAttribute
        attr = root.GetAttributeNode("ISBN")

        ' Display the value of the attribute.
        Dim attrValue As String
        attrValue = attr.InnerXml
        Console.WriteLine(attrValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

 public class Sample
 {
      public static void Main()
      {
    XmlDocument doc = new XmlDocument();
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +
                   "<title>The Handmaid's Tale</title>" +
                   "<price>14.95</price>" +
                   "</book>");

    // Move to an element.
     XmlElement root = doc.DocumentElement;

    // Get an attribute.
     XmlAttribute attr = root.GetAttributeNode("ISBN");

    // Display the value of the attribute.
     String attrValue = attr.InnerXml;
     Console.WriteLine(attrValue);

    }
}
```

<span data-ttu-id="10d68-133">Sie können auch wie im vorherigen Beispiel vorgehen, in dem ein einzelner Attributknoten aus einer Attributauflistung abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="10d68-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="10d68-134">Im folgenden Beispiel wird dargestellt, wie eine Codezeile geschrieben werden kann, damit ein einzelnes Attribut nach der Indexnummer aus dem Stamm der XML-Dokumentstruktur abgerufen wird, auch als **DocumentElement**-Eigenschaft bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="10d68-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>

```csharp
XmlAttribute attr = doc.DocumentElement.Attributes[0];
```

## <a name="see-also"></a><span data-ttu-id="10d68-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10d68-135">See also</span></span>

- [<span data-ttu-id="10d68-136">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="10d68-136">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
