---
title: Einführung in XML-Literale in Visual Basic2
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: 9f5c54574e51c537d9ea58d307afda10736d0d88
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266949"
---
# <a name="introduction-to-xml-literals-in-visual-basic"></a>Einführung in XML-Literale in Visual Basic
Dieser Abschnitt enthält Informationen zum Erstellen von XML-Strukturen in Visual Basic.  
  
 Informationen zur Verwendung der Ergebnisse von LINQ-Abfragen als Inhalt für eine XML-Struktur finden Sie unter [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).  
  
 Weitere Informationen zu XML-Literalen in Visual Basic finden Sie unter [Übersicht über LINQ zu XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).  
  
## <a name="creating-xml-trees"></a>Erstellen von XML-Strukturen  
 Im folgenden Beispiel wird gezeigt, wie Sie ein <xref:System.Xml.Linq.XElement>, in diesem Fall `contacts`, erstellen können.  
  
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
  
### <a name="creating-an-xelement-with-simple-content"></a>Erstellen eines "XElement" mit einfachem Inhalt  
 Ein <xref:System.Xml.Linq.XElement> mit einfachem Inhalt können Sie wie folgt erstellen:  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)
```  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a>Erstellen eines leeren Elements  
 Ein leeres <xref:System.Xml.Linq.XElement> können Sie wie folgt erstellen:  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a>Verwenden von eingebetteten Ausdrücken  
 Eine wichtige Funktion von XML-Literalen besteht darin, dass sie eingebettete Ausdrücke zulassen. Mit eingebetteten Ausdrücken können Sie Ausdrücke auswerten und die Ergebnisse eines Ausdrucks in die XML-Struktur einfügen. Wenn die Auswertung des Ausdrucks einen <xref:System.Xml.Linq.XElement>-Typ ergibt, wird ein Element in die Struktur eingefügt. Wenn die Auswertung des Ausdrucks einen <xref:System.Xml.Linq.XAttribute>-Typ ergibt, wird ein Attribut in die Struktur eingefügt. Sie können Elemente und Attribute nur an den Stellen in die Struktur einfügen, an denen sie gültig sind.  
  
 Dabei muss beachtet werden, dass ein eingebetteter Ausdruck nur einen einzelnen Ausdruck enthalten kann. Das Einbetten mehrerer Anweisungen ist nicht möglich. Wenn ein Ausdruck sich über eine einzelne Zeile hinaus erstreckt, müssen Sie das Zeilenfortsetzungszeichen verwenden.  
  
 Wenn Sie einen eingebetteten Ausdruck zum Hinzufügen vorhandener Knoten (inklusive Elementen) und Attribute zu einer neuen XML-Struktur verwenden und die vorhandenen Knoten bereits ein übergeordnetes Element besitzen, werden die Knoten geklont, und die neu geklonten Knoten werden an die neue XML-Struktur angefügt. Wenn die vorhandenen Knoten keine übergeordneten Elemente besitzen, werden sie einfach an die neue XML-Struktur angefügt. Dies wird im letzten Beispiel in diesem Thema gezeigt.  
  
 Das folgende Beispiel verwendet zum Einfügen eines Elements in die Struktur einen eingebetteten Ausdruck:  
  
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
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a>Verwenden von eingebetteten Ausdrücken für Inhalt  
 Sie können mit eingebetteten Ausdrücken Elemente mit Inhalt versehen:  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a>Verwenden einer LINQ-Abfrage in einem eingebetteten Ausdruck  
 Sie können die Ergebnisse einer LINQ-Abfrage für den Inhalt eines Elements verwenden:  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a>Verwenden von eingebetteten Ausdrücken für Knotennamen  
 Sie können eingebettete Ausdrücke auch zum Berechnen von Attributnamen, Attributwerten, Elementnamen und Elementwerten verwenden:  
  
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
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a>Klonen kontra Anfügen  
 Wie oben erwähnt: Wenn Sie einen eingebetteten Ausdruck zum Hinzufügen vorhandener Knoten (inklusive Elementen) und Attribute zu einer neuen XML-Struktur verwenden und die vorhandenen Knoten bereits ein übergeordnetes Element besitzen, werden die Knoten geklont, und die neu geklonten Knoten werden an die neue XML-Struktur angefügt. Besitzen die vorhandenen Knoten hingegen keine übergeordneten Elemente, werden sie einfach an die neue XML-Struktur angefügt.  
  
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
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```console  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
