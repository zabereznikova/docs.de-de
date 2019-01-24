---
title: 'Vorgehensweise: Abrufen eines einzelnes Attributs (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
ms.openlocfilehash: 73f5a252bd207edaa14aead42a6f122c3320423e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704679"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a>Vorgehensweise: Abrufen eines einzelnes Attributs (LINQ to XML) (Visual Basic)
In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen Attributs eines Elements anhand des Attributsnamens erläutert. Diese Vorgehensweise eignet sich für das Schreiben von Abfrageausdrücken, mit denen Sie nach einem Element mit einem bestimmten Attribut suchen möchten.  
  
 Die <xref:System.Xml.Linq.XElement.Attribute%2A>-Methode der <xref:System.Xml.Linq.XElement>-Klasse gibt das <xref:System.Xml.Linq.XAttribute> mit dem angegebenen Namen zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Xml.Linq.XElement.Attribute%2A>-Methode verwendet:  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 Dieses Beispiel ermittelt zuerst alle Nachfolger in der Struktur mit dem Namen `Phone` und dann das Attribut mit dem Namen `type`.  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
home  
work  
```  
  
## <a name="example"></a>Beispiel  
 Wenn Sie den Wert des Attributs abrufen möchten, können Sie es einfach genauso umwandeln, wie Sie es bei <xref:System.Xml.Linq.XElement>-Objekten machen würden. Dies wird im folgenden Beispiel veranschaulicht:  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet explizite Umwandlungsoperatoren für die Umwandlung der <xref:System.Xml.Linq.XAttribute>-Klasse in `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält denselben Code für ein Attribut, das sich in einem Namespace befindet. Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
home  
work  
```  
  
## <a name="see-also"></a>Siehe auch
- [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
