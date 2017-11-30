---
title: Zugreifen auf die Attribute im DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="194d1-102">Zugreifen auf die Attribute im DOM</span><span class="sxs-lookup"><span data-stu-id="194d1-102">Accessing Attributes in the DOM</span></span>
<span data-ttu-id="194d1-103">Attribute sind Eigenschaften des Elements und keine untergeordneten Elemente des entsprechenden Elements.</span><span class="sxs-lookup"><span data-stu-id="194d1-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="194d1-104">Dies stellt aufgrund der Methoden zum Navigieren zwischen nebengeordneten, übergeordneten und untergeordneten Knoten des XML-Dokumentobjektmodells (DOM) eine wichtige Unterscheidung dar.</span><span class="sxs-lookup"><span data-stu-id="194d1-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="194d1-105">Z. B. die **PreviousSibling** und **NextSibling** Methoden werden nicht zum Navigieren von einem Element zu einem Attribut oder zwischen Attributen.</span><span class="sxs-lookup"><span data-stu-id="194d1-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="194d1-106">Stattdessen ein Attribut ist eine Eigenschaft eines Elements und ist im Besitz eines Elements, verfügt über eine **OwnerElement** Eigenschaft und keine **ParentNode** -Eigenschaft, und verfügt über unterschiedliche Methoden der Navigation.</span><span class="sxs-lookup"><span data-stu-id="194d1-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>  
  
 <span data-ttu-id="194d1-107">Wenn der aktuelle Knoten ein Element ist, verwenden Sie die **HasAttribute** Methode, um festzustellen, ob alle Attribute, die dem Element zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="194d1-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="194d1-108">Wenn bekannt ist, dass ein Element Attribute besitzt, bestehen mehrere Möglichkeiten, um auf die Attribute zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="194d1-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="194d1-109">Um ein einzelnes Attribut aus dem Element abzurufen, können Sie die **GetAttribute** und **GetAttributeNode** Methoden die **XmlElement** oder erhalten Sie alle Attribute in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="194d1-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="194d1-110">Es ist hilfreich, eine Auflistung abzurufen, wenn Sie die Auflistung durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="194d1-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="194d1-111">Wenn Sie alle Attribute des Elements möchten, verwenden die **Attribute** Eigenschaft des Elements, das alle Attribute in einer Auflistung abzufragen.</span><span class="sxs-lookup"><span data-stu-id="194d1-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>  
  
## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="194d1-112">Abfragen aller Attribute in einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="194d1-112">Retrieving All Attributes into a Collection</span></span>  
 <span data-ttu-id="194d1-113">Rufen Sie gegebenenfalls alle versetzen die Attribute eines Elementknotens in eine Auflistung der **XmlElement.Attributes** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="194d1-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="194d1-114">Dadurch wird die **XmlAttributeCollection** , das alle Attribute eines Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="194d1-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="194d1-115">Die **XmlAttributeCollection** Klasse erbt von der **XmlNamedNode** Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="194d1-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="194d1-116">Daher die Methoden und Eigenschaften, die in der Auflistung verfügbaren enthalten auf einer Karte benannten Knoten verfügbar sind. darüber hinaus an Methoden und Eigenschaften, die spezifisch für die **XmlAttributeCollection** Klasse, z. B. die **ItemOf**  Eigenschaft oder die **Append** Methode.</span><span class="sxs-lookup"><span data-stu-id="194d1-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="194d1-117">Jedes Element in der attributauflistung stellt einen **XmlAttribute** Knoten.</span><span class="sxs-lookup"><span data-stu-id="194d1-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="194d1-118">Um die Anzahl der Attribute für ein Element zu suchen, erhalten die **XmlAttributeCollection**, und verwenden die **Anzahl** Eigenschaft, um wie viele **XmlAttribute** Knoten werden in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="194d1-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>  
  
 <span data-ttu-id="194d1-119">Im folgenden Codebeispiel wird veranschaulicht, wie eine attributauflistung mit der **Anzahl** Methode für den Schleifenindex durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="194d1-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="194d1-120">Im folgenden Code wird dargestellt, wie ein einzelnes Attribut aus einer Auflistung abgefragt und dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="194d1-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>  
  
```vb  
Imports System  
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
  
 <span data-ttu-id="194d1-121">In diesem Beispiel wird die folgende Ausgabe dargestellt:</span><span class="sxs-lookup"><span data-stu-id="194d1-121">This example displays the following output:</span></span>  
  
 <span data-ttu-id="194d1-122">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="194d1-122">**Output**</span></span>  
  
 <span data-ttu-id="194d1-123">Alle Attribute in der Auflistung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="194d1-123">Display all the attributes in the collection.</span></span>  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 <span data-ttu-id="194d1-124">Die Informationen in einer Attributauflistung können nach Namen oder Indexnummer abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="194d1-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="194d1-125">Im oben aufgeführten Beispiel wird dargestellt, wie Daten nach Namen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="194d1-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="194d1-126">Im nächsten Beispiel wird dargestellt, wie Daten nach Indexnummer abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="194d1-126">The next example shows how to retrieve data by index number.</span></span>  
  
 <span data-ttu-id="194d1-127">Da die **XmlAttributeCollection** ist eine Auflistung durchlaufen werden kann, und wählen Sie Namen oder Index, in diesem Beispiel wird gezeigt, Auswählen des ersten Attributs aus der Auflistung mithilfe eines nullbasierten Index, und verwenden die folgende Datei **baseuri.xml**als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="194d1-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>  
  
### <a name="input"></a><span data-ttu-id="194d1-128">Eingabe</span><span class="sxs-lookup"><span data-stu-id="194d1-128">Input</span></span>  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
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
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
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
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="194d1-129">Abrufen eines einzelnen Attributknotens</span><span class="sxs-lookup"><span data-stu-id="194d1-129">Retrieving an Individual Attribute Node</span></span>  
 <span data-ttu-id="194d1-130">Zum Abrufen eines einzelnen Attributknotens aus einem Element wird die <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="194d1-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="194d1-131">Es gibt ein Objekt des Typs **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="194d1-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="194d1-132">Nachdem Sie haben eine **XmlAttribute**, alle Methoden und Eigenschaften verfügbar, in der <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> Klasse stehen für dieses Objekt, wie das Suchen nach der **OwnerElement**.</span><span class="sxs-lookup"><span data-stu-id="194d1-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>  
  
```vb  
Imports System  
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
  
 <span data-ttu-id="194d1-133">Sie können auch wie im vorherigen Beispiel vorgehen, in dem ein einzelner Attributknoten aus einer Attributauflistung abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="194d1-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="194d1-134">Im folgenden Codebeispiel wird veranschaulicht wie eine Codezeile kann zum Abrufen eines einzelnen Attributs anhand der Indexnummer aus dem Stamm der XML-Dokument geschrieben werden, auch bekannt als Struktur die **DocumentElement** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="194d1-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a><span data-ttu-id="194d1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="194d1-135">See Also</span></span>  
 [<span data-ttu-id="194d1-136">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="194d1-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
