---
title: Programmieren mit Knoten (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 52fb60b95b869a79900f84c2a1a7a6151bb5b58f
ms.lasthandoff: 03/13/2017

---
# <a name="programming-with-nodes-visual-basic"></a>Programmieren mit Knoten (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Entwickler, die Programme, wie einen XML-Editor, ein Transformationssystem oder einen Berichts-Generator schreiben müssen, müssen häufig Programme schreiben, die auf einer detaillierteren Ebene als Elemente und Attribute arbeiten. Sie müssen oft auf der Ebene der Knoten arbeiten und dabei Textknoten, Verarbeitungsanweisungen und Kommentare bearbeiten. Dieses Thema beschäftigt sich mit einigen Aspekten des Programmierens auf Knotenebene.  
  
## <a name="node-details"></a>Knotendetails  
 Es gibt eine Reihe von Programmierdetails, die ein auf der Knotenebene arbeitender Programmierer kennen sollte.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>Übergeordnete Eigenschaft der untergeordneten XDocument-Knoten ist gleich NULL  
 Die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft enthält das übergeordnete <xref:System.Xml.Linq.XElement>, nicht den übergeordneten Knoten.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XObject.Parent%2A> Untergeordnete Knoten <xref:System.Xml.Linq.XDocument>gibt es kein übergeordnetes <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> Das übergeordnete Element ist das Dokument, damit der <xref:System.Xml.Linq.XObject.Parent%2A>für diesen Knoten festgelegt ist auf Null.</xref:System.Xml.Linq.XObject.Parent%2A>  
  
 Dies wird im folgenden Beispiel veranschaulicht:  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Textknoten können nebeneinander liegen  
 In einer Reihe von XML-Programmiermodellen werden nebeneinander liegende Textknoten immer zusammengeführt. Dies wird mitunter als Normalisierung von Textknoten bezeichnet. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] findet keine Normalisierung von Textknoten statt. Wenn Sie einem Element zwei Textknoten hinzufügen, erhalten Sie zwei nebeneinander liegende Textknoten. Aber wenn Sie den Inhalt als Zeichenfolge statt als hinzufügen ein <xref:System.Xml.Linq.XText>Knoten [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] kann die Zeichenfolge mit einem benachbarten Textknoten zusammenführen.</xref:System.Xml.Linq.XText>  
  
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
  
```  
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
  
```  
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
  
```  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Namespaces sind Attribute in der LINQ to XML-Struktur  
 Auch wenn Namespacedeklarationen dieselbe Syntax wie Attribute haben, werden Namespacedeklarationen in einigen Programmierschnittstellen, wie XSLT und XPath, nicht als Attribute betrachtet. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], Namespaces befinden sich als <xref:System.Xml.Linq.XAttribute>Objekte in der XML-Struktur.</xref:System.Xml.Linq.XAttribute> Wenn Sie die Attribute für ein Element durchlaufen, das eine Namespacedeklaration enthält, wird die Namespacedeklaration als eines der Elemente in der zurückgegebenen Auflistung angezeigt.  
  
 Die <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>-Eigenschaft gibt an, ob ein Attribut eine Namespacedeklaration ist.</xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>  
  
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
  
```  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>XPath-Achsenmethoden geben keinen untergeordneten XDocument-Leerraum zurück  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]ermöglicht untergeordnete Textknoten ein <xref:System.Xml.Linq.XDocument>, solange die Textknoten nur Leerraum enthalten.</xref:System.Xml.Linq.XDocument> Allerdings das XPath-Objektmodell enthält keinen Leerraum als untergeordnete Knoten eines Dokuments, also beim Durchlaufen der untergeordneten Elemente ein <xref:System.Xml.Linq.XDocument>mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A>-Achse Leerraumtextknoten zurückgegeben.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XDocument> Allerdings beim Durchlaufen der untergeordneten Elemente ein <xref:System.Xml.Linq.XDocument>mit den XPath-Achsenmethoden, Leerraum-Textknoten werden nicht zurückgegeben werden.</xref:System.Xml.Linq.XDocument>  
  
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
  
```  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>XDeclaration-Objekte sind keine Knoten  
 Beim Durchlaufen der untergeordneten Knoten von einem <xref:System.Xml.Linq.XDocument>, wird das XML-Deklarationsobjekt nicht angezeigt.</xref:System.Xml.Linq.XDocument> Es ist kein untergeordneter Knoten des Dokuments, sondern eine seiner Eigenschaften.  
  
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
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte LINQ to XML-Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
