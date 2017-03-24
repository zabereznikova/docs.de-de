---
title: "Gewusst wie: Schreiben von Abfragen für XML in Namespaces (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5af26b7ec0a2ab465917cd0ee62f65a97f5f0e40
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a>Gewusst wie: Schreiben von Abfragen für XML in Namespaces (Visual Basic)
Um eine Abfrage für XML zu schreiben, die in einem Namespace befindet, verwenden Sie <xref:System.Xml.Linq.XName>Objekte, die den richtigen Namespace enthalten.</xref:System.Xml.Linq.XName>  
  
 In Visual Basic wird meist ein globaler Namespace definiert, und anschließend werden XML-Literale und XML-Eigenschaften verwendet, die den globalen Namespace nutzen. Sie können einen globalen Standardnamespace definieren. Die Elemente in den XML-Literalen sind dann standardmäßig im Namespace vorhanden. Stattdessen können Sie auch einen globalen Namespace mit einem Präfix definieren und dann das Präfix den Anforderungen entsprechend in den XML-Literalen und in den XML-Eigenschaften verwenden. Wie bei anderen XML-Formen auch befinden sich Attribute standardmäßig nicht in einem Namespace.  
  
 Der erste Satz von Beispielen in diesem Thema veranschaulicht, wie eine XML-Struktur in einem Standardnamespace erstellen. Der zweite Satz veranschaulicht, wie eine XML-Struktur in einem Namespace mit einem Präfix zu erstellen.  
  
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
  
```  
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
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
