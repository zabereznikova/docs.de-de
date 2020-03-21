---
title: Programmieren mit Knoten
ms.date: 07/20/2015
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
ms.openlocfilehash: b2c9022cb57cf122af47bbe6d1a7fe2b4d41327c
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266962"
---
# <a name="programming-with-nodes-visual-basic"></a>Programmierung mit Knoten (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Entwickler, die Programme, wie einen XML-Editor, ein Transformationssystem oder einen Berichts-Generator schreiben müssen, müssen häufig Programme schreiben, die auf einer detaillierteren Ebene als Elemente und Attribute arbeiten. Sie müssen oft auf der Ebene der Knoten arbeiten und dabei Textknoten, Verarbeitungsanweisungen und Kommentare bearbeiten. Dieses Thema beschäftigt sich mit einigen Aspekten des Programmierens auf Knotenebene.  
  
## <a name="node-details"></a>Knotendetails  
 Es gibt eine Reihe von Programmierdetails, die ein auf der Knotenebene arbeitender Programmierer kennen sollte.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>Übergeordnete Eigenschaft der untergeordneten XDocument-Knoten ist gleich NULL  
 Die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft enthält das übergeordnete <xref:System.Xml.Linq.XElement>, nicht den übergeordneten Knoten. Für untergeordnete Knoten von <xref:System.Xml.Linq.XDocument> gibt es kein übergeordnetes <xref:System.Xml.Linq.XElement>. Ihr übergeordnetes Element ist das Dokument, weshalb die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft dieser Knoten gleich NULL ist.  
  
 Dies wird im folgenden Beispiel veranschaulicht:  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Textknoten können nebeneinander liegen  
 In einer Reihe von XML-Programmiermodellen werden nebeneinander liegende Textknoten immer zusammengeführt. Dies wird mitunter als Normalisierung von Textknoten bezeichnet. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] findet keine Normalisierung von Textknoten statt. Wenn Sie einem Element zwei Textknoten hinzufügen, erhalten Sie zwei nebeneinander liegende Textknoten. Wird jedoch Inhalt in Form einer Zeichenfolge statt als <xref:System.Xml.Linq.XText>-Knoten hinzugefügt, kann [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Zeichenfolge mit einem angrenzenden Textknoten zusammenführen.  
  
 Dies wird im folgenden Beispiel veranschaulicht:  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
' This does not add a new text node.  
xmlTree.Add("new content")  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
'// This does add a new, adjacent text node.  
xmlTree.Add(New XText("more text"))  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a>Textknoten können leer sein  
 In einigen XML-Programmiermodellen ist garantiert, dass Textknoten keine leere Zeichenfolge enthalten. Der Grund dafür ist, dass ein Textknoten keine Auswirkungen auf die Serialisierung des XML-Codes haben. Aber aus demselben Grund, aus dem Textknoten nebeneinander liegen können, wird der Textknoten auch nicht gelöscht, wenn Sie den Text aus ihm entfernen, indem Sie eine leere Zeichenfolge als Wert für den Textknoten festlegen.  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a>Ein leerer Textknoten wirkt sich auf die Serialisierung aus  
 Wenn ein Element nur einen untergeordneten Textknoten enthält, der leer ist, wird es mit der langen Tagsyntax serialisiert: `<Child></Child>`. Wenn ein Element überhaupt keine untergeordneten Knoten enthält, wird es mit der kurzen Tagsyntax serialisiert: `<Child />`.  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Namespaces sind Attribute in der LINQ to XML-Struktur  
 Auch wenn Namespacedeklarationen dieselbe Syntax wie Attribute haben, werden Namespacedeklarationen in einigen Programmierschnittstellen, wie XSLT und XPath, nicht als Attribute betrachtet. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] werden Namespaces jedoch als <xref:System.Xml.Linq.XAttribute>-Objekte in der XML-Struktur gespeichert. Wenn Sie die Attribute für ein Element durchlaufen, das eine Namespacedeklaration enthält, wird die Namespacedeklaration als eines der Elemente in der zurückgegebenen Auflistung angezeigt.  
  
 Die <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>-Eigenschaft gibt an, ob ein Attribut eine Namespacedeklaration ist.  
  
```vb  
Dim root As XElement = _
<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>  
For Each att As XAttribute In root.Attributes()  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, _  
                      att.IsNamespaceDeclaration)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>XPath-Achsenmethoden geben keinen untergeordneten XDocument-Leerraum zurück  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ermöglicht untergeordnete Textknoten eines <xref:System.Xml.Linq.XDocument>, solange die Textknoten nur Leerraum enthalten. Das XPath-Objektmodell sieht jedoch keinen Leerraum als untergeordnete Knoten eines Dokuments vor. Das hat zur Folge, dass beim Durchlaufen der untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument> mit der <xref:System.Xml.Linq.XContainer.Nodes%2A>-Achse Leerraumtextknoten zurückgegeben werden. Werden dagegen die untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument> mit den XPath-Achsenmethoden durchlaufen, erfolgt keine Rückgabe von Leerraumtextknoten.  
  
```vb  
' Create a document with some white space child nodes of the document.  
Dim root As XDocument = XDocument.Parse( _  
"<?xml version='1.0' encoding='utf-8' standalone='yes'?>" & _  
vbNewLine & "<Root/>" & vbNewLine & "<!--a comment-->" & vbNewLine, _  
LoadOptions.PreserveWhitespace)  
  
' Count the white space child nodes using LINQ to XML.  
Console.WriteLine(root.Nodes().OfType(Of XText)().Count())  
  
' Count the white space child nodes using XPathEvaluate.  
Dim nodes As IEnumerable = CType(root.XPathEvaluate("text()"), IEnumerable)  
Console.WriteLine(nodes.OfType(Of XText)().Count())  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>XDeclaration-Objekte sind keine Knoten  
 Wenn Sie die untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument>-Objekts durchlaufen, wird das XML-Deklarationsobjekt nicht angezeigt. Es ist kein untergeordneter Knoten des Dokuments, sondern eine seiner Eigenschaften.  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterte LINQ-zu-XML-Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
