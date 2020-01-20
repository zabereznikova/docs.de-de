---
title: 'Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Strukturen in eine XSLT-Formatvorlage (C#)'
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 109e1a49530f34e7197f8c975de8c04245b11734
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347295"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a><span data-ttu-id="394a8-102">Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Strukturen in eine XSLT-Formatvorlage (C#)</span><span class="sxs-lookup"><span data-stu-id="394a8-102">How to use annotations to transform LINQ to XML trees in an XSLT style (C#)</span></span>
<span data-ttu-id="394a8-103">Sie können Anmerkungen verwenden, um das Transformieren von XML-Strukturen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="394a8-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="394a8-104">Einige XML-Dokumente sind "dokumentorientiert mit gemischtem Inhalt".</span><span class="sxs-lookup"><span data-stu-id="394a8-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="394a8-105">Bei solchen Dokumenten kennen Sie nicht unbedingt die Form der untergeordneten Knoten eines Elements.</span><span class="sxs-lookup"><span data-stu-id="394a8-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="394a8-106">So könnte z. B. ein Knoten, der Text enthält, wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="394a8-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="394a8-107">Pro vorhandenem Textknoten kann eine unbegrenzte Anzahl untergeordneter `<b>`-Elemente und `<i>`-Elemente vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="394a8-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="394a8-108">Dieser Ansatz lässt sich auf eine Reihe anderer Situationen erweitern, z.B. auf Seiten, die verschiedene untergeordnete Elemente enthalten, wie normale Absätze, Absätze mit Aufzählungszeichen und Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="394a8-108">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="394a8-109">Zellen in einer Tabelle können Text, Dropdownlisten oder Bitmaps enthalten.</span><span class="sxs-lookup"><span data-stu-id="394a8-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="394a8-110">Eine der wichtigsten Eigenschaften von dokumentorientiertem XML besteht darin, dass Sie nicht wissen, welche untergeordneten Elemente ein bestimmtes Element besitzen wird.</span><span class="sxs-lookup"><span data-stu-id="394a8-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="394a8-111">Wenn Sie Elemente in einer Struktur transformieren möchten und nicht wirklich viel über die untergeordneten Elemente der Elemente wissen, die transformiert werden sollen, bietet sich die Verwendung von Anmerkungen als effektiver Ansatz an.</span><span class="sxs-lookup"><span data-stu-id="394a8-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="394a8-112">Dieser Ansatz sieht, grob zusammengefasst, wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="394a8-112">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="394a8-113">Zuerst werden die Elemente in der Struktur mit einem Ersetzungselement mit einer Anmerkung versehen.</span><span class="sxs-lookup"><span data-stu-id="394a8-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="394a8-114">Danach wird die gesamte Struktur durchlaufen, wobei eine neue Struktur erstellt wird, in der alle Elemente durch ihre Anmerkung ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="394a8-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="394a8-115">Dieses Beispiel implementiert die Iteration und die Erstellung der neuen Struktur mit einer Funktion mit dem Namen `XForm`.</span><span class="sxs-lookup"><span data-stu-id="394a8-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="394a8-116">Genauer gesagt setzt sich der Ansatz aus folgenden Schritten zusammen:</span><span class="sxs-lookup"><span data-stu-id="394a8-116">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="394a8-117">Führen Sie mindestens eine LINQ to XML-Abfrage aus, die den Satz von Elementen zurückgibt, die Sie in eine andere Form transformieren möchten.</span><span class="sxs-lookup"><span data-stu-id="394a8-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="394a8-118">Fügen Sie für jedes Element in der Abfrage ein neues <xref:System.Xml.Linq.XElement>-Objekt als Anmerkung zum Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="394a8-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="394a8-119">Dieses neue Element ersetzt in der neuen, transformierten Struktur das Element, das Sie mit der Anmerkung versehen haben.</span><span class="sxs-lookup"><span data-stu-id="394a8-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="394a8-120">Das folgende Beispiel zeigt, dass der dazu zu schreibende Code recht einfach ist:</span><span class="sxs-lookup"><span data-stu-id="394a8-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="394a8-121">Das neue Element, das als Anmerkung hinzugefügt wird, kann neue untergeordnete Knoten enthalten, und es kann eine Teilstruktur jeder beliebigen Form bilden.</span><span class="sxs-lookup"><span data-stu-id="394a8-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="394a8-122">Dabei gilt folgende spezielle Regel: Wenn sich ein untergeordneter Knoten des neuen Elements in einem anderen Namespace befindet, einem Namespace, der zu diesem Zweck erfunden wurde (in diesem Beispiel lautet der Namespace `http://www.microsoft.com/LinqToXmlTransform/2007`), wird dieses untergeordnete Element nicht in die neue Struktur kopiert.</span><span class="sxs-lookup"><span data-stu-id="394a8-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="394a8-123">Stattdessen gilt: Wenn es sich bei dem Namespace um den oben erwähnten speziellen Namespace handelt und der lokale Name des Elements `ApplyTransforms` lautet, dann werden die untergeordneten Knoten des Elements in der ursprünglichen Struktur durchlaufen und in die neue Struktur kopiert (mit der Ausnahme, dass mit Anmerkungen versehene untergeordnete Elemente diesen Regeln entsprechend selbst transformiert werden).</span><span class="sxs-lookup"><span data-stu-id="394a8-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="394a8-124">Dies entspricht in gewissem Maße der Spezifikation von Transformationen in XSL.</span><span class="sxs-lookup"><span data-stu-id="394a8-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="394a8-125">Die Abfrage, die einen Satz von Knoten auswählt, entspricht dem XPath-Ausdruck für eine Vorlage.</span><span class="sxs-lookup"><span data-stu-id="394a8-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="394a8-126">Der Code zum Erstellen des neuen <xref:System.Xml.Linq.XElement>, das als Anmerkung gespeichert wird, entspricht dem Sequenzkonstruktor in XSL, und das `ApplyTransforms`-Element entspricht von seiner Funktion her dem `xsl:apply-templates`-Element in XSL.</span><span class="sxs-lookup"><span data-stu-id="394a8-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="394a8-127">Ein Vorteil dieses Ansatzes besteht darin, dass Sie beim Formulieren von Abfragen stets Abfragen für die nicht geänderte Quellstruktur schreiben.</span><span class="sxs-lookup"><span data-stu-id="394a8-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="394a8-128">Sie müssen sich damit keine Gedanken machen, wie sich Änderungen an der Struktur auf die Abfragen auswirken, die Sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="394a8-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="394a8-129">Transformieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="394a8-129">Transforming a Tree</span></span>  
 <span data-ttu-id="394a8-130">Bei diesem ersten Beispiel werden alle `Paragraph`-Knoten in `para` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="394a8-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement root = XElement.Parse(@"  
<Root>  
    <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
    <Paragraph>More text.</Paragraph>  
</Root>");  
  
// replace Paragraph with para  
foreach (var el in root.Descendants("Paragraph"))  
    el.AddAnnotation(  
        new XElement("para",  
            // same idea as xsl:apply-templates  
            new XElement(xf + "ApplyTransforms")  
        )  
    );  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newRoot = XForm(root);  
  
Console.WriteLine(newRoot);  
```  
  
 <span data-ttu-id="394a8-131">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="394a8-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="394a8-132">Kompliziertere Transformation</span><span class="sxs-lookup"><span data-stu-id="394a8-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="394a8-133">Das folgende Beispiel fragt die Struktur ab, berechnet den Durchschnitt und die Summe der `Data`-Elemente und fügt diese als neue Elemente zur Struktur hinzu.</span><span class="sxs-lookup"><span data-stu-id="394a8-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement data = new XElement("Root",  
    new XElement("Data", 20),  
    new XElement("Data", 10),  
    new XElement("Data", 3)  
);  
  
// while adding annotations, you can query the source tree all you want,  
// as the tree is not mutated while annotating.
var avg = data.Elements("Data").Select(z => (Decimal)z).Average();
data.AddAnnotation(  
    new XElement("Root",  
        new XElement(xf + "ApplyTransforms"),  
        new XElement("Average", $"{avg:F4}"),
        new XElement("Sum",  
            data  
            .Elements("Data")  
            .Select(z => (int)z)  
            .Sum()  
        )  
    )  
);  
  
Console.WriteLine("Before Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(data);  
Console.WriteLine();  
Console.WriteLine();  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newData = XForm(data);  
  
Console.WriteLine("After Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="394a8-134">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="394a8-134">This example produces the following output:</span></span>  
  
```output  
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
  
## <a name="effecting-the-transform"></a><span data-ttu-id="394a8-135">Ausführen der Transformation</span><span class="sxs-lookup"><span data-stu-id="394a8-135">Effecting the Transform</span></span>  
 <span data-ttu-id="394a8-136">Eine kleine Funktion, `XForm`, erstellt aus der ursprünglichen, mit Anmerkungen versehenen Struktur eine neue transformierte Struktur.</span><span class="sxs-lookup"><span data-stu-id="394a8-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="394a8-137">Der Pseudocode für die Funktion ist recht einfach:</span><span class="sxs-lookup"><span data-stu-id="394a8-137">The pseudo code for the function is quite simple:</span></span>  
  
```text  
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
  
 <span data-ttu-id="394a8-138">Es folgt die Implementierung dieser Funktion:</span><span class="sxs-lookup"><span data-stu-id="394a8-138">Following is the implementation of this function:</span></span>  
  
```csharp  
// Build a transformed XML tree per the annotations  
static XElement XForm(XElement source)  
{  
    XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    XName at = xf + "ApplyTransforms";  
  
    if (source.Annotation<XElement>() != null)  
    {  
        XElement anno = source.Annotation<XElement>();  
        return new XElement(anno.Name,  
            anno.Attributes(),  
            anno  
            .Nodes()  
            .Select(  
                (XNode n) =>  
                {  
                    XElement annoEl = n as XElement;  
                    if (annoEl != null)  
                    {  
                        if (annoEl.Name == at)  
                            return (object)(  
                                source.Nodes()  
                                .Select(  
                                    (XNode n2) =>  
                                    {  
                                        XElement e2 = n2 as XElement;  
                                        if (e2 == null)  
                                            return n2;  
                                        else  
                                            return XForm(e2);  
                                    }  
                                )  
                            );  
                        else  
                            return n;  
                    }  
                    else  
                        return n;  
                }  
            )  
        );  
    }  
    else  
    {  
        return new XElement(source.Name,  
            source.Attributes(),  
            source  
                .Nodes()  
                .Select(n =>  
                {  
                    XElement el = n as XElement;  
                    if (el == null)  
                        return n;  
                    else  
                        return XForm(el);  
                }  
                )  
        );  
    }  
}   
```  
  
## <a name="complete-example"></a><span data-ttu-id="394a8-139">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="394a8-139">Complete Example</span></span>  
 <span data-ttu-id="394a8-140">Der folgende Code ist ein vollständiges Beispiel, das die `XForm`-Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="394a8-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="394a8-141">Er beinhaltet einige typische Verwendungen dieser Transformationsart:</span><span class="sxs-lookup"><span data-stu-id="394a8-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Xml;  
using System.Xml.Linq;  
  
class Program  
{  
    static XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    static XName at = xf + "ApplyTransforms";  
  
    // Build a transformed XML tree per the annotations  
    static XElement XForm(XElement source)  
    {  
        if (source.Annotation<XElement>() != null)  
        {  
            XElement anno = source.Annotation<XElement>();  
            return new XElement(anno.Name,  
                anno.Attributes(),  
                anno  
                .Nodes()  
                .Select(  
                    (XNode n) =>  
                    {  
                        XElement annoEl = n as XElement;  
                        if (annoEl != null)  
                        {  
                            if (annoEl.Name == at)  
                                return (object)(  
                                    source.Nodes()  
                                    .Select(  
                                        (XNode n2) =>  
                                        {  
                                            XElement e2 = n2 as XElement;  
                                            if (e2 == null)  
                                                return n2;  
                                            else  
                                                return XForm(e2);  
                                        }  
                                    )  
                                );  
                            else  
                                return n;  
                        }  
                        else  
                            return n;  
                    }  
                )  
            );  
        }  
        else  
        {  
            return new XElement(source.Name,  
                source.Attributes(),  
                source  
                    .Nodes()  
                    .Select(n =>  
                    {  
                        XElement el = n as XElement;  
                        if (el == null)  
                            return n;  
                        else  
                            return XForm(el);  
                    }  
                    )  
            );  
        }  
    }  
  
    static void Main(string[] args)  
    {  
        XElement root = new XElement("Root",  
            new XComment("A comment"),  
            new XAttribute("Att1", 123),  
            new XElement("Child", 1),  
            new XElement("Child", 2),  
            new XElement("Other",  
                new XElement("GC", 3),  
                new XElement("GC", 4)  
            ),  
            XElement.Parse(  
              "<SomeMixedContent>This is <i>an</i> element that " +  
              "<b>has</b> some mixed content</SomeMixedContent>"),  
            new XElement("AnUnchangedElement", 42)  
        );  
  
        // each of the following serves the same semantic purpose as  
        // XSLT templates and sequence constructors  
  
        // replace Child with NewChild  
        foreach (var el in root.Elements("Child"))  
            el.AddAnnotation(new XElement("NewChild", (string)el));  
  
        // replace first GC with GrandChild, add an attribute  
        foreach (var el in root.Descendants("GC").Take(1))  
            el.AddAnnotation(  
                new XElement("GrandChild",  
                    new XAttribute("ANewAttribute", 999),  
                    (string)el  
                )  
            );  
  
        // replace Other with NewOther, add new child elements around original content  
        foreach (var el in root.Elements("Other"))  
            el.AddAnnotation(  
                new XElement("NewOther",  
                    new XElement("MyNewChild", 1),  
                    // same idea as xsl:apply-templates  
                    new XElement(xf + "ApplyTransforms"),  
                    new XElement("ChildThatComesAfter")  
                )  
            );  
  
        // change name of element that has mixed content  
        root.Descendants("SomeMixedContent").First().AddAnnotation(  
            new XElement("MixedContent",  
                new XElement(xf + "ApplyTransforms")  
            )  
        );  
  
        // replace <b> with <Bold>  
        foreach (var el in root.Descendants("b"))  
            el.AddAnnotation(  
                new XElement("Bold",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        // replace <i> with <Italic>  
        foreach (var el in root.Descendants("i"))  
            el.AddAnnotation(  
                new XElement("Italic",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        Console.WriteLine("Before Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(root);  
        Console.WriteLine();  
        Console.WriteLine();  
        XElement newRoot = XForm(root);  
  
        Console.WriteLine("After Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(newRoot);  
    }  
}  
```  
  
 <span data-ttu-id="394a8-142">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="394a8-142">This example produces the following output:</span></span>  
  
```output  
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
  