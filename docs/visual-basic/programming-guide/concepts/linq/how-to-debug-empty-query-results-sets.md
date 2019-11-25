---
title: 'Gewusst wie: Debuggen von leeren Abfrageergebnissätzen'
ms.date: 07/20/2015
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
ms.openlocfilehash: 21c161a702338c0c6943fa09212deaea7fdd72f9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353075"
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a>How to: Debug Empty Query Results Sets (Visual Basic)

Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.

Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen und dann nicht ordnungsgemäß abgefragt wird.

Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.

For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.

```vb
Dim root As XElement = _
    <Root xmlns='http://www.adventure-works.com'>
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
Console.WriteLine("Result set follows:")
For Each el As XElement In c1
    Console.WriteLine(el.Value)
Next
Console.WriteLine("End of result set")
```

Dieses Beispiel liefert das folgende Ergebnis:

```console
Result set follows:
End of result set
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.

The solution is to declare and initialize a global default namespace. Dadurch werden alle XML-Eigenschaften im Standardnamespace platziert. Weitere Änderungen sind für das ordnungsgemäße Funktionieren des Beispiels nicht erforderlich.

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root xmlns='http://www.adventure-works.com'>
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
        Console.WriteLine("Result set follows:")
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

Dieses Beispiel liefert das folgende Ergebnis:

```console
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a>Siehe auch

- [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
