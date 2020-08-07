---
title: 'Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Strukturen in eine XSLT-Formatvorlage (C#)'
description: Erfahren Sie, wie Sie Anmerkungen verwenden, um LINQ to XML-Strukturen in eine XSLT-Formatvorlage zu transformieren. Hier finden Sie ein Beispiel für die Transformation einer Struktur mithilfe der XForm-Funktion.
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 844ca08cb2c6b47f7803d388663daeacb65bdb68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302879"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a>Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Strukturen in eine XSLT-Formatvorlage (C#)
Sie können Anmerkungen verwenden, um das Transformieren von XML-Strukturen zu ermöglichen.  
  
 Einige XML-Dokumente sind "dokumentorientiert mit gemischtem Inhalt". Bei solchen Dokumenten kennen Sie nicht unbedingt die Form der untergeordneten Knoten eines Elements. So könnte z. B. ein Knoten, der Text enthält, wie folgt aussehen:  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 Pro vorhandenem Textknoten kann eine unbegrenzte Anzahl untergeordneter `<b>`-Elemente und `<i>`-Elemente vorhanden sein. Dieser Ansatz lässt sich auf eine Reihe anderer Situationen erweitern, z.B. auf Seiten, die verschiedene untergeordnete Elemente enthalten, wie normale Absätze, Absätze mit Aufzählungszeichen und Bitmaps. Zellen in einer Tabelle können Text, Dropdownlisten oder Bitmaps enthalten. Eine der wichtigsten Eigenschaften von dokumentorientiertem XML besteht darin, dass Sie nicht wissen, welche untergeordneten Elemente ein bestimmtes Element besitzen wird.  
  
 Wenn Sie Elemente in einer Struktur transformieren möchten und nicht wirklich viel über die untergeordneten Elemente der Elemente wissen, die transformiert werden sollen, bietet sich die Verwendung von Anmerkungen als effektiver Ansatz an.  
  
 Dieser Ansatz sieht, grob zusammengefasst, wie folgt aus:  
  
- Zuerst werden die Elemente in der Struktur mit einem Ersetzungselement mit einer Anmerkung versehen.  
  
- Danach wird die gesamte Struktur durchlaufen, wobei eine neue Struktur erstellt wird, in der alle Elemente durch ihre Anmerkung ersetzt werden. Dieses Beispiel implementiert die Iteration und die Erstellung der neuen Struktur mit einer Funktion mit dem Namen `XForm`.  
  
 Genauer gesagt setzt sich der Ansatz aus folgenden Schritten zusammen:  
  
- Führen Sie mindestens eine LINQ to XML-Abfrage aus, die den Satz von Elementen zurückgibt, die Sie in eine andere Form transformieren möchten. Fügen Sie für jedes Element in der Abfrage ein neues <xref:System.Xml.Linq.XElement>-Objekt als Anmerkung zum Element hinzu. Dieses neue Element ersetzt in der neuen, transformierten Struktur das Element, das Sie mit der Anmerkung versehen haben. Das folgende Beispiel zeigt, dass der dazu zu schreibende Code recht einfach ist:  
  
- Das neue Element, das als Anmerkung hinzugefügt wird, kann neue untergeordnete Knoten enthalten, und es kann eine Teilstruktur jeder beliebigen Form bilden.  
  
- Dabei gilt folgende spezielle Regel: Wenn sich ein untergeordneter Knoten des neuen Elements in einem anderen Namespace befindet, einem Namespace, der zu diesem Zweck erfunden wurde (in diesem Beispiel lautet der Namespace `http://www.microsoft.com/LinqToXmlTransform/2007`), wird dieses untergeordnete Element nicht in die neue Struktur kopiert. Stattdessen gilt: Wenn es sich bei dem Namespace um den oben erwähnten speziellen Namespace handelt und der lokale Name des Elements `ApplyTransforms` lautet, dann werden die untergeordneten Knoten des Elements in der ursprünglichen Struktur durchlaufen und in die neue Struktur kopiert (mit der Ausnahme, dass mit Anmerkungen versehene untergeordnete Elemente diesen Regeln entsprechend selbst transformiert werden).  
  
- Dies entspricht in gewissem Maße der Spezifikation von Transformationen in XSL. Die Abfrage, die einen Satz von Knoten auswählt, entspricht dem XPath-Ausdruck für eine Vorlage. Der Code zum Erstellen des neuen <xref:System.Xml.Linq.XElement>, das als Anmerkung gespeichert wird, entspricht dem Sequenzkonstruktor in XSL, und das `ApplyTransforms`-Element entspricht von seiner Funktion her dem `xsl:apply-templates`-Element in XSL.  
  
- Ein Vorteil dieses Ansatzes besteht darin, dass Sie beim Formulieren von Abfragen stets Abfragen für die nicht geänderte Quellstruktur schreiben. Sie müssen sich damit keine Gedanken machen, wie sich Änderungen an der Struktur auf die Abfragen auswirken, die Sie schreiben.  
  
## <a name="transforming-a-tree"></a>Transformieren einer Struktur  
 Bei diesem ersten Beispiel werden alle `Paragraph`-Knoten in `para` umbenannt.  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a>Kompliziertere Transformation  
 Das folgende Beispiel fragt die Struktur ab, berechnet den Durchschnitt und die Summe der `Data`-Elemente und fügt diese als neue Elemente zur Struktur hinzu.  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
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
  
## <a name="effecting-the-transform"></a>Ausführen der Transformation  
 Eine kleine Funktion, `XForm`, erstellt aus der ursprünglichen, mit Anmerkungen versehenen Struktur eine neue transformierte Struktur.  
  
- Der Pseudocode für die Funktion ist recht einfach:  
  
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
  
 Es folgt die Implementierung dieser Funktion:  
  
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
  
## <a name="complete-example"></a>Vollständiges Beispiel  
 Der folgende Code ist ein vollständiges Beispiel, das die `XForm`-Funktion enthält. Er beinhaltet einige typische Verwendungen dieser Transformationsart:  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
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
  