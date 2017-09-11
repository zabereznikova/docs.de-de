---
title: "Einführung in XML-Literalen in Visual Basic2 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a3aff4755c23664153ce1dc0ec2df58a96d29c66
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-xml-literals-in-visual-basic"></a><span data-ttu-id="3cf27-102">Einführung in XML-Literale in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cf27-102">Introduction to XML Literals in Visual Basic</span></span>
<span data-ttu-id="3cf27-103">Dieser Abschnitt enthält Informationen zum Erstellen von XML-Strukturen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cf27-103">This section provides information about creating XML trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="3cf27-104">Informationen zur Verwendung der Ergebnisse von LINQ-Abfragen als Inhalt für eine XML-Struktur finden Sie unter [funktionale Konstruktion (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3cf27-104">For information about using the results of LINQ queries as the content for an XML tree, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3cf27-105">Weitere Informationen zu XML-Literalen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], finden Sie unter [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3cf27-105">For more information on XML literals in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], see [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="3cf27-106">Erstellen von XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="3cf27-106">Creating XML Trees</span></span>  
 <span data-ttu-id="3cf27-107">Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Xml.Linq.XElement>, in diesem Fall `contacts`:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3cf27-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
### <a name="creating-an-xelement-with-simple-content"></a><span data-ttu-id="3cf27-108">Erstellen eines "XElement" mit einfachem Inhalt</span><span class="sxs-lookup"><span data-stu-id="3cf27-108">Creating an XElement with Simple Content</span></span>  
 <span data-ttu-id="3cf27-109">Sie erstellen ein <xref:System.Xml.Linq.XElement>, der einfachen Inhalt wie folgt enthält:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3cf27-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)   
```  
  
 <span data-ttu-id="3cf27-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-110">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="3cf27-111">Erstellen eines leeren Elements</span><span class="sxs-lookup"><span data-stu-id="3cf27-111">Creating an Empty Element</span></span>  
 <span data-ttu-id="3cf27-112">Sie können eine leere erstellen <xref:System.Xml.Linq.XElement>wie folgt:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3cf27-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="3cf27-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-113">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a><span data-ttu-id="3cf27-114">Verwenden von eingebetteten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="3cf27-114">Using Embedded Expressions</span></span>  
 <span data-ttu-id="3cf27-115">Ein wichtiges Merkmal von XML-Literalen besteht darin, dass sie eingebettete Ausdrücke zulassen.</span><span class="sxs-lookup"><span data-stu-id="3cf27-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="3cf27-116">Mit eingebetteten Ausdrücken können Sie Ausdrücke auswerten und die Ergebnisse eines Ausdrucks in die XML-Struktur einfügen.</span><span class="sxs-lookup"><span data-stu-id="3cf27-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="3cf27-117">Ergibt der Ausdruck einen Typ von <xref:System.Xml.Linq.XElement>, wird ein Element in die Struktur eingefügt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3cf27-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="3cf27-118">Ergibt der Ausdruck einen Typ von <xref:System.Xml.Linq.XAttribute>, ein Attribut in die Struktur eingefügt.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="3cf27-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="3cf27-119">Sie können Elemente und Attribute nur an den Stellen in die Struktur einfügen, an denen sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="3cf27-119">You can insert elements and attributes into the tree only where they are valid.</span></span>  
  
 <span data-ttu-id="3cf27-120">Dabei muss beachtet werden, dass ein eingebetteter Ausdruck nur einen einzelnen Ausdruck enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="3cf27-120">It is important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="3cf27-121">Das Einbetten mehrerer Anweisungen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="3cf27-121">You cannot embed multiple statements.</span></span> <span data-ttu-id="3cf27-122">Wenn ein Ausdruck sich über eine einzelne Zeile hinaus erstreckt, müssen Sie das Zeilenfortsetzungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cf27-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>  
  
 <span data-ttu-id="3cf27-123">Wenn Sie einen eingebetteten Ausdruck zum Hinzufügen vorhandener Knoten (inklusive Elementen) und Attribute zu einer neuen XML-Struktur verwenden und die vorhandenen Knoten bereits ein übergeordnetes Element besitzen, werden die Knoten geklont,</span><span class="sxs-lookup"><span data-stu-id="3cf27-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="3cf27-124">und die neu geklonten Knoten werden an die neue XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="3cf27-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="3cf27-125">Wenn die vorhandenen Knoten keine übergeordneten Elemente besitzen, werden sie einfach an die neue XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="3cf27-125">If the existing nodes are not parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="3cf27-126">Dies wird im letzten Beispiel in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3cf27-126">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="3cf27-127">Das folgende Beispiel verwendet zum Einfügen eines Elements in die Struktur einen eingebetteten Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="3cf27-127">The following example uses an embedded expression to insert an element into the tree:</span></span>  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 <span data-ttu-id="3cf27-128">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a><span data-ttu-id="3cf27-129">Verwenden von eingebetteten Ausdrücken für Inhalt</span><span class="sxs-lookup"><span data-stu-id="3cf27-129">Using Embedded Expressions for Content</span></span>  
 <span data-ttu-id="3cf27-130">Sie können mit eingebetteten Ausdrücken Elemente mit Inhalt versehen:</span><span class="sxs-lookup"><span data-stu-id="3cf27-130">You can use an embedded expression to supply the content of an element:</span></span>  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="3cf27-131">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-131">This example produces the following output:</span></span>  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="3cf27-132">Verwenden einer LINQ-Abfrage in einem eingebetteten Ausdruck</span><span class="sxs-lookup"><span data-stu-id="3cf27-132">Using a LINQ Query in an Embedded Expression</span></span>  
 <span data-ttu-id="3cf27-133">Sie können die Ergebnisse einer LINQ-Abfrage für den Inhalt eines Elements verwenden:</span><span class="sxs-lookup"><span data-stu-id="3cf27-133">You can use the results of a LINQ query for the content of an element:</span></span>  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="3cf27-134">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-134">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a><span data-ttu-id="3cf27-135">Verwenden von eingebetteten Ausdrücken für Knotennamen</span><span class="sxs-lookup"><span data-stu-id="3cf27-135">Using Embedded Expressions for Node Names</span></span>  
 <span data-ttu-id="3cf27-136">Sie können eingebettete Ausdrücke auch zum Berechnen von Attributnamen, Attributwerten, Elementnamen und Elementwerten verwenden:</span><span class="sxs-lookup"><span data-stu-id="3cf27-136">You can also use embedded expressions to calculate attribute names, attribute values, element names, and element values:</span></span>  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="3cf27-137">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-137">This example produces the following output:</span></span>  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a><span data-ttu-id="3cf27-138">Klonen oder Anfügen?</span><span class="sxs-lookup"><span data-stu-id="3cf27-138">Cloning vs. Attaching</span></span>  
 <span data-ttu-id="3cf27-139">Wie oben erwähnt: Wenn Sie einen eingebetteten Ausdruck zum Hinzufügen vorhandener Knoten (inklusive Elementen) und Attribute zu einer neuen XML-Struktur verwenden und die vorhandenen Knoten bereits ein übergeordnetes Element besitzen, werden die Knoten geklont, und die neu geklonten Knoten werden an die neue XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="3cf27-139">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, if the existing nodes are already parented, the nodes are cloned and the newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="3cf27-140">Besitzen die vorhandenen Knoten hingegen keine übergeordneten Elemente, werden sie einfach an die neue XML-Struktur angefügt.</span><span class="sxs-lookup"><span data-stu-id="3cf27-140">If the existing nodes are not parented, they are simply attached to the new XML tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="3cf27-141">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3cf27-141">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cf27-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cf27-142">See Also</span></span>  
 [<span data-ttu-id="3cf27-143">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cf27-143">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
