---
title: 'Gewusst wie: Filtern nach einem optionalen Element'
ms.date: 07/20/2015
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
ms.openlocfilehash: e67cb58710d49a19f322b3555efa96ac69b9f654
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353044"
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a>Gewusst wie: Filtern nach einem optionalen Element (Visual Basic)
Es kann vorkommen, dass Sie nach einem Element filtern möchten, ohne genau zu wissen, ob dieses Element in Ihrem XML-Dokument tatsächlich existiert. Die Suche sollte dann so ausgeführt werden, dass für den Fall, dass das Element das gesuchte untergeordnete Element nicht besitzt, beim Filtern keine Ausnahme wegen eines NULL-Verweises ausgelöst wird. Im folgenden Beispiel besitzt das `Child5`-Element kein untergeordnetes `Type`-Element, dennoch wird die Abfrage korrekt ausgeführt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Xml.Linq.Extensions.Elements%2A>-Erweiterungsmethode:  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```console  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```console  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [Grundlegende Abfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Untergeordnete XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Projektions Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
