---
title: 'Gewusst wie: Schreiben von XML-Abfragen in Namespaces'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 496cf8daf5136e8aafff000312bbd730a5152e9f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344470"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a>Gewusst wie: Schreiben von Abfragen für XML in Namespaces (Visual Basic)
Wenn Sie eine Abfrage für XML in einem Namespace schreiben möchten, müssen Sie <xref:System.Xml.Linq.XName>-Objekte verwenden, die den richtigen Namespace enthalten.  
  
 In Visual Basic wird meist ein globaler Namespace definiert, und anschließend werden XML-Literale und XML-Eigenschaften verwendet, die den globalen Namespace nutzen. Sie können einen globalen Standardnamespace definieren. Die Elemente in den XML-Literalen sind dann standardmäßig im Namespace vorhanden. Stattdessen können Sie auch einen globalen Namespace mit einem Präfix definieren und dann das Präfix den Anforderungen entsprechend in den XML-Literalen und in den XML-Eigenschaften verwenden. Wie bei anderen XML-Formen auch befinden sich Attribute standardmäßig nicht in einem Namespace.  
  
 Die erste Gruppe der Beispiele in diesem Thema zeigt,wie Sie eine XML-Struktur in einem Standardnamespace erstellen. Die zweite Gruppe der Beispiele zeigt, wie Sie eine XML-Struktur in einem Namespace mit einem Präfix erstellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Standardnamespace befindet. Anschließend ruft das Beispiel eine Auflistung der Elemente ab.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a>Beispiel  
 In Visual Basic unterscheidet sich das Schreiben von Abfragen für eine XML-Struktur, die einen Namespace mit einem Präfix verwendet, jedoch recht stark vom Abfragen einer XML-Struktur in einem Standardnamespace. Normalerweise verwenden Sie die `Imports`-Anweisung, um den Namespace mit einem Präfix zu importieren. Anschließend können Sie das Präfix beim Erstellen der XML-Struktur in den Element- und Attributnamen verwenden. Sie können das Präfix auch beim Abfragen einer XML-Struktur mithilfe von XML-Eigenschaften verwenden.  
  
 Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Namespace mit einem Präfix befindet. Anschließend ruft das Beispiel eine Auflistung der Elemente ab.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
