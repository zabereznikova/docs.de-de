---
title: Programmieren mit Knoten (C#)
description: Erfahren Sie mehr über das Programmieren mit Knoten. Hiermit können Entwickler Programme schreiben, die auf detaillierterer Ebene arbeiten, als Elemente und Attribute bieten können.
ms.date: 07/20/2015
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 8a31d6459ab644a682d480239cabc3d88fd7dc14
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301683"
---
# <a name="programming-with-nodes-c"></a>Programmieren mit Knoten (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Entwickler, die Programme, wie einen XML-Editor, ein Transformationssystem oder einen Berichts-Generator schreiben müssen, müssen häufig Programme schreiben, die auf einer detaillierteren Ebene als Elemente und Attribute arbeiten. Sie müssen oft auf der Ebene der Knoten arbeiten und dabei Textknoten, Verarbeitungsanweisungen und Kommentare bearbeiten. Dieses Thema beschäftigt sich mit einigen Aspekten des Programmierens auf Knotenebene.  
  
## <a name="node-details"></a>Knotendetails  
 Es gibt eine Reihe von Programmierdetails, die ein auf der Knotenebene arbeitender Programmierer kennen sollte.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>Übergeordnete Eigenschaft der untergeordneten XDocument-Knoten ist gleich NULL  
 Die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft enthält das übergeordnete <xref:System.Xml.Linq.XElement>, nicht den übergeordneten Knoten. Für untergeordnete Knoten von <xref:System.Xml.Linq.XDocument> gibt es kein übergeordnetes <xref:System.Xml.Linq.XElement>. Ihr übergeordnetes Element ist das Dokument, weshalb die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft dieser Knoten gleich NULL ist.  
  
 Dies wird im folgenden Beispiel veranschaulicht:  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Textknoten können nebeneinander liegen  
 In einer Reihe von XML-Programmiermodellen werden nebeneinander liegende Textknoten immer zusammengeführt. Dies wird mitunter als Normalisierung von Textknoten bezeichnet. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] findet keine Normalisierung von Textknoten statt. Wenn Sie einem Element zwei Textknoten hinzufügen, erhalten Sie zwei nebeneinander liegende Textknoten. Wird jedoch Inhalt in Form einer Zeichenfolge statt als <xref:System.Xml.Linq.XText>-Knoten hinzugefügt, kann [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Zeichenfolge mit einem angrenzenden Textknoten zusammenführen.  
  
 Dies wird im folgenden Beispiel veranschaulicht:  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a>Textknoten können leer sein  
 In einigen XML-Programmiermodellen ist garantiert, dass Textknoten keine leere Zeichenfolge enthalten. Der Grund dafür ist, dass ein Textknoten keine Auswirkungen auf die Serialisierung des XML-Codes haben. Aber aus demselben Grund, aus dem Textknoten nebeneinander liegen können, wird der Textknoten auch nicht gelöscht, wenn Sie den Text aus ihm entfernen, indem Sie eine leere Zeichenfolge als Wert für den Textknoten festlegen.  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a>Ein leerer Textknoten wirkt sich auf die Serialisierung aus  
 Wenn ein Element nur einen untergeordneten Textknoten enthält, der leer ist, wird es mit der langen Tagsyntax serialisiert: `<Child></Child>`. Wenn ein Element überhaupt keine untergeordneten Knoten enthält, wird es mit der kurzen Tagsyntax serialisiert: `<Child />`.  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Namespaces sind Attribute in der LINQ to XML-Struktur  
 Auch wenn Namespacedeklarationen dieselbe Syntax wie Attribute haben, werden Namespacedeklarationen in einigen Programmierschnittstellen, wie XSLT und XPath, nicht als Attribute betrachtet. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] werden Namespaces jedoch als <xref:System.Xml.Linq.XAttribute>-Objekte in der XML-Struktur gespeichert. Wenn Sie die Attribute für ein Element durchlaufen, das eine Namespacedeklaration enthält, wird die Namespacedeklaration als eines der Elemente in der zurückgegebenen Auflistung angezeigt.  
  
 Die <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>-Eigenschaft gibt an, ob ein Attribut eine Namespacedeklaration ist.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>XPath-Achsenmethoden geben keinen untergeordneten XDocument-Leerraum zurück  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ermöglicht untergeordnete Textknoten eines <xref:System.Xml.Linq.XDocument>, solange die Textknoten nur Leerraum enthalten. Das XPath-Objektmodell sieht jedoch keinen Leerraum als untergeordnete Knoten eines Dokuments vor. Das hat zur Folge, dass beim Durchlaufen der untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument> mit der <xref:System.Xml.Linq.XContainer.Nodes%2A>-Achse Leerraumtextknoten zurückgegeben werden. Werden dagegen die untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument> mit den XPath-Achsenmethoden durchlaufen, erfolgt keine Rückgabe von Leerraumtextknoten.  
  
```csharp  
// Create a document with some white-space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white-space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white-space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>XDeclaration-Objekte sind keine Knoten  
 Wenn Sie die untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument>-Objekts durchlaufen, wird das XML-Deklarationsobjekt nicht angezeigt. Es ist kein untergeordneter Knoten des Dokuments, sondern eine seiner Eigenschaften.  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  