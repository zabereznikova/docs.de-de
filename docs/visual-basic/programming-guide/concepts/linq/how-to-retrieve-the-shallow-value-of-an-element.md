---
title: 'Vorgehensweise: Abrufen des Shallow-Werts eines Elements (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
ms.openlocfilehash: a861acafe3b9561b1237e6b6449374374c723805
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505796"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a>Vorgehensweise: Abrufen des Shallow-Werts eines Elements (Visual Basic)
In diesem Thema wird gezeigt, wie Sie den flachen Wert eines Elements abrufen. Der flache Wert ist ausschließlich der Wert des jeweiligen Elements, im Gegensatz zum tiefen Wert, der die Werte aller Nachfolgerelemente enthält, die zu einer einzelnen Zeichenkette verkettet werden.  
  
 Beim Abrufen des Elementwerts mithilfe des Umwandlungsverfahrens oder der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft wird der tiefe Wert abgerufen. Um den flachen Wert abzurufen, können Sie die `ShallowValue`-Erweiterungsmethode verwenden, wie im folgenden Beispiel gezeigt wird. Das Abrufen des flachen Werts ist nützlich, wenn Sie Elemente anhand ihrer Inhalte auswählen möchten.  
  
 Im folgenden Beispiel wird eine Erweiterungsmethode deklariert, die den flachen Wert eines Elements abruft. Anschließend wird die Erweiterungsmethode in einer Abfrage verwendet, um alle Elemente aufzulisten, die einen berechneten Wert enthalten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die folgende Textdatei, Report.xml, als Quelldatei verwendet.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```vb  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function ShallowValue(ByVal xe As XElement)  
        Return xe _  
               .Nodes() _  
               .OfType(Of XText)() _  
               .Aggregate(New StringBuilder(), _  
                              Function(s, c) s.Append(c), _  
                              Function(s) s.ToString())  
    End Function  
  
    Sub Main()  
        Dim root As XElement = XElement.Load("Report.xml")  
  
        Dim query As IEnumerable(Of XElement) = _  
            From el In root.Descendants() _  
            Where (el.ShallowValue().StartsWith("=")) _  
            Select el  
  
        For Each q As XElement In query  
            Console.WriteLine("{0}{1}{2}", _  
                q.Name.ToString().PadRight(8), _  
                q.Attribute("Name").ToString().PadRight(20), _  
                q.ShallowValue())  
        Next  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Siehe auch
- [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
