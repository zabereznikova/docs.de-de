---
title: 'Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Bäumen in eine XSLT-Formatvorlage (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: 9ebff2276fc9f574989530fdb07a0d0875ff74a3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648814"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a><span data-ttu-id="3c13a-102">Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Bäumen in eine XSLT-Formatvorlage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c13a-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>
<span data-ttu-id="3c13a-103">Sie können Anmerkungen verwenden, um das Transformieren von XML-Strukturen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c13a-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="3c13a-104">Einige XML-Dokumente sind "dokumentorientiert mit gemischtem Inhalt".</span><span class="sxs-lookup"><span data-stu-id="3c13a-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="3c13a-105">Bei solchen Dokumenten kennen Sie nicht unbedingt die Form der untergeordneten Knoten eines Elements.</span><span class="sxs-lookup"><span data-stu-id="3c13a-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="3c13a-106">So könnte z. B. ein Knoten, der Text enthält, wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="3c13a-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="3c13a-107">Pro vorhandenem Textknoten kann eine unbegrenzte Anzahl untergeordneter `<b>`-Elemente und `<i>`-Elemente vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3c13a-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="3c13a-108">Dieser Ansatz führt zu einer Reihe anderer Situationen: z. B. Seiten, die eine Vielzahl von untergeordneten Elementen, z. B. normale Absätze, Absätze mit Aufzählungszeichen und Bitmaps enthalten können.</span><span class="sxs-lookup"><span data-stu-id="3c13a-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="3c13a-109">Zellen in einer Tabelle können Text, Dropdownlisten oder Bitmaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c13a-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="3c13a-110">Eine der wichtigsten Eigenschaften von dokumentorientiertem XML besteht darin, dass Sie nicht wissen, welche untergeordneten Elemente ein bestimmtes Element besitzen wird.</span><span class="sxs-lookup"><span data-stu-id="3c13a-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="3c13a-111">Wenn Sie Elemente in einer Struktur transformieren möchten und nicht wirklich viel über die untergeordneten Elemente der Elemente wissen, die transformiert werden sollen, bietet sich die Verwendung von Anmerkungen als effektiver Ansatz an.</span><span class="sxs-lookup"><span data-stu-id="3c13a-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="3c13a-112">Dieser Ansatz sieht, grob zusammengefasst, wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="3c13a-112">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="3c13a-113">Zuerst werden die Elemente in der Struktur mit einem Ersetzungselement mit einer Anmerkung versehen.</span><span class="sxs-lookup"><span data-stu-id="3c13a-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="3c13a-114">Danach wird die gesamte Struktur durchlaufen, wobei eine neue Struktur erstellt wird, in der alle Elemente durch ihre Anmerkung ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3c13a-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="3c13a-115">Dieses Beispiel implementiert die Iteration und die Erstellung der neuen Struktur mit einer Funktion mit dem Namen `XForm`.</span><span class="sxs-lookup"><span data-stu-id="3c13a-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="3c13a-116">Genauer gesagt setzt sich der Ansatz aus folgenden Schritten zusammen:</span><span class="sxs-lookup"><span data-stu-id="3c13a-116">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="3c13a-117">Führen Sie mindestens eine LINQ to XML-Abfrage aus, die den Satz von Elementen zurückgibt, die Sie in eine andere Form transformieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3c13a-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="3c13a-118">Fügen Sie für jedes Element in der Abfrage ein neues <xref:System.Xml.Linq.XElement>-Objekt als Anmerkung zum Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c13a-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="3c13a-119">Dieses neue Element ersetzt in der neuen, transformierten Struktur das Element, das Sie mit der Anmerkung versehen haben.</span><span class="sxs-lookup"><span data-stu-id="3c13a-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="3c13a-120">Das folgende Beispiel zeigt, dass der dazu zu schreibende Code recht einfach ist:</span><span class="sxs-lookup"><span data-stu-id="3c13a-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="3c13a-121">Das neue Element, das als Anmerkung hinzugefügt wird, kann neue untergeordnete Knoten enthalten, und es kann eine Teilstruktur jeder beliebigen Form bilden.</span><span class="sxs-lookup"><span data-stu-id="3c13a-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="3c13a-122">Dabei gilt folgende spezielle Regel: Wenn sich ein untergeordneter Knoten des neuen Elements in einem anderen Namespace befindet, einem Namespace, der zu diesem Zweck erfunden wurde (in diesem Beispiel lautet der Namespace `http://www.microsoft.com/LinqToXmlTransform/2007`), wird dieses untergeordnete Element nicht in die neue Struktur kopiert.</span><span class="sxs-lookup"><span data-stu-id="3c13a-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="3c13a-123">Stattdessen gilt: Wenn es sich bei dem Namespace um den oben erwähnten speziellen Namespace handelt und der lokale Name des Elements `ApplyTransforms` lautet, dann werden die untergeordneten Knoten des Elements in der ursprünglichen Struktur durchlaufen und in die neue Struktur kopiert (mit der Ausnahme, dass mit Anmerkungen versehene untergeordnete Elemente diesen Regeln entsprechend selbst transformiert werden).</span><span class="sxs-lookup"><span data-stu-id="3c13a-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="3c13a-124">Dies entspricht in gewissem Maße der Spezifikation von Transformationen in XSL.</span><span class="sxs-lookup"><span data-stu-id="3c13a-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="3c13a-125">Die Abfrage, die einen Satz von Knoten auswählt, entspricht dem XPath-Ausdruck für eine Vorlage.</span><span class="sxs-lookup"><span data-stu-id="3c13a-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="3c13a-126">Der Code zum Erstellen des neuen <xref:System.Xml.Linq.XElement>, das als Anmerkung gespeichert wird, entspricht dem Sequenzkonstruktor in XSL, und das `ApplyTransforms`-Element entspricht von seiner Funktion her dem `xsl:apply-templates`-Element in XSL.</span><span class="sxs-lookup"><span data-stu-id="3c13a-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="3c13a-127">Ein Vorteil dieses Ansatzes besteht darin, dass Sie beim Formulieren von Abfragen stets Abfragen für die nicht geänderte Quellstruktur schreiben.</span><span class="sxs-lookup"><span data-stu-id="3c13a-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="3c13a-128">Sie müssen sich damit keine Gedanken machen, wie sich Änderungen an der Struktur auf die Abfragen auswirken, die Sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="3c13a-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="3c13a-129">Transformieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="3c13a-129">Transforming a Tree</span></span>  
 <span data-ttu-id="3c13a-130">Bei diesem ersten Beispiel werden alle `Paragraph`-Knoten in `para` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="3c13a-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
                <Paragraph>More text.</Paragraph>  
            </Root>  
  
        ' Replace Paragraph with p.  
        For Each el In root...<Paragraph>  
            ' same idea as xsl:apply-templates  
            el.AddAnnotation( _  
                <para>  
                    <<%= at %>></>  
                </para>)  
        Next  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newRoot As XElement = XForm(root)  
        Console.WriteLine(newRoot)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="3c13a-131">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3c13a-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="3c13a-132">Kompliziertere Transformation</span><span class="sxs-lookup"><span data-stu-id="3c13a-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="3c13a-133">Das folgende Beispiel fragt die Struktur ab, berechnet den Durchschnitt und die Summe der `Data`-Elemente und fügt diese als neue Elemente zur Struktur hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c13a-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim data As XElement = _  
            <Root>  
                <Data>20</Data>  
                <Data>10</Data>  
                <Data>3</Data>  
            </Root>  
  
        ' While adding annotations, you can query the source tree all you want,  
        ' as the tree is not mutated while annotating.  
        data.AddAnnotation( _  
            <Root>  
                <<%= at %>/>  
                <Average>  
                    <%= _  
                        String.Format("{0:F4}", _  
                        data.Elements("Data") _  
                        .Select(Function(z) CDec(z)).Average()) _  
                    %>  
                </Average>  
                <Sum>  
                    <%= _  
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _  
                    %>  
                </Sum>  
            </Root> _  
        )  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(data)  
        Console.WriteLine(vbNewLine)  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newData As XElement = XForm(data)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newData)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="3c13a-134">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3c13a-134">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
</Root>  
  
After Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
  <Average>11.0000</Average>  
  <Sum>33</Sum>  
</Root>  
```  
  
## <a name="effecting-the-transform"></a><span data-ttu-id="3c13a-135">Ausführen der Transformation</span><span class="sxs-lookup"><span data-stu-id="3c13a-135">Effecting the Transform</span></span>  
 <span data-ttu-id="3c13a-136">Eine kleine Funktion, `XForm`, erstellt aus der ursprünglichen, mit Anmerkungen versehenen Struktur eine neue transformierte Struktur.</span><span class="sxs-lookup"><span data-stu-id="3c13a-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="3c13a-137">Der Pseudocode für die Funktion ist recht einfach:</span><span class="sxs-lookup"><span data-stu-id="3c13a-137">The pseudo code for the function is quite simple:</span></span>  
  
```  
The function takes an XElement as an argument and returns an XElement.   
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="3c13a-138">Es folgt die Implementierung dieser Funktion:</span><span class="sxs-lookup"><span data-stu-id="3c13a-138">Following is the implementation of this function:</span></span>  
  
```vb  
' Build a transformed XML tree per the annotations.  
Function XForm(ByVal source As XElement) As XElement  
    If source.Annotation(Of XElement)() IsNot Nothing Then  
        Dim anno As XElement = source.Annotation(Of XElement)()  
        Return _  
            <<%= anno.Name.ToString() %>>  
                <%= anno.Attributes() %>  
                <%= anno.Nodes().Select(Function(n As XNode) _  
                    GetSubNodes(n, source)) %>  
            </>  
    Else  
        Return _  
            <<%= source.Name %>>  
                <%= source.Attributes() %>  
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
            </>  
    End If  
End Function  
  
Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
    Dim annoEl As XElement = TryCast(n, XElement)  
    If annoEl IsNot Nothing Then  
        If annoEl.Name = at Then  
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
        End If  
    End If  
    Return n  
End Function  
  
Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
    Dim e2 As XElement = TryCast(n2, XElement)  
    If e2 Is Nothing Then  
        Return n2  
    Else  
        Return XForm(e2)  
    End If  
End Function  
```  
  
## <a name="complete-example"></a><span data-ttu-id="3c13a-139">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c13a-139">Complete Example</span></span>  
 <span data-ttu-id="3c13a-140">Der folgende Code ist ein vollständiges Beispiel, das die `XForm`-Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="3c13a-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="3c13a-141">Er beinhaltet einige typische Verwendungen dieser Transformationsart:</span><span class="sxs-lookup"><span data-stu-id="3c13a-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Linq  
Imports System.Text  
Imports System.Xml  
Imports System.Xml.Linq  
  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    ' Build a transformed XML tree per the annotations.  
    Function XForm(ByVal source As XElement) As XElement  
        If source.Annotation(Of XElement)() IsNot Nothing Then  
            Dim anno As XElement = source.Annotation(Of XElement)()  
            Return _  
                <<%= anno.Name.ToString() %>>  
                    <%= anno.Attributes() %>  
                    <%= anno.Nodes().Select(Function(n As XNode) _  
                        GetSubNodes(n, source)) %>  
                </>  
        Else  
            Return _  
                <<%= source.Name %>>  
                    <%= source.Attributes() %>  
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
                </>  
        End If  
    End Function  
  
    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
        Dim annoEl As XElement = TryCast(n, XElement)  
        If annoEl IsNot Nothing Then  
            If annoEl.Name = at Then  
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
            End If  
        End If  
        Return n  
    End Function  
  
    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
        Dim e2 As XElement = TryCast(n2, XElement)  
        If e2 Is Nothing Then  
            Return n2  
        Else  
            Return XForm(e2)  
        End If  
    End Function  
  
    Sub Main()  
        Dim root As XElement = _  
<Root Att1='123'>  
    <!--A comment-->  
    <Child>1</Child>  
    <Child>2</Child>  
    <Other>  
        <GC>3</GC>  
        <GC>4</GC>  
    </Other>  
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
    <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
        ' Each of the following serves the same semantic purpose as  
        ' XSLT templates and sequence constructors.  
  
        ' Replace Child with NewChild.  
        For Each el In root.<Child>  
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)  
        Next  
  
        ' Replace first GC with GrandChild, add an attribute.  
        For Each el In root...<GC>.Take(1)  
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)  
        Next  
  
        ' Replace Other with NewOther, add new child elements around original content.  
        For Each el In root.<Other>  
            el.AddAnnotation( _  
                <NewOther>  
                    <MyNewChild>1</MyNewChild>  
                    <<%= at %>></>  
                    <ChildThatComesAfter/>  
                </NewOther>)  
        Next  
  
        ' Change name of element that has mixed content.  
        root...<SomeMixedContent>(0).AddAnnotation( _  
                <MixedContent><<%= at %>></></MixedContent>)  
  
        ' Replace <b> with <Bold>.  
        For Each el In root...<b>  
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)  
        Next  
  
        ' Replace <i> with <Italic>.  
        For Each el In root...<i>  
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)  
        Next  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(root)  
        Console.WriteLine(vbNewLine)  
        Dim newRoot As XElement = XForm(root)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newRoot)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="3c13a-142">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3c13a-142">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <Child>1</Child>  
  <Child>2</Child>  
  <Other>  
    <GC>3</GC>  
    <GC>4</GC>  
  </Other>  
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
After Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <NewChild>1</NewChild>  
  <NewChild>2</NewChild>  
  <NewOther>  
    <MyNewChild>1</MyNewChild>  
    <GrandChild ANewAttribute="999">3</GrandChild>  
    <GC>4</GC>  
    <ChildThatComesAfter />  
  </NewOther>  
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c13a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c13a-143">See also</span></span>

- [<span data-ttu-id="3c13a-144">Erweiterte LINQ to XML-Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c13a-144">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
