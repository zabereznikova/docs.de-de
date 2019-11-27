---
title: 'Gewusst wie: Abrufen eines einzelnes untergeordneten Elements (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
ms.openlocfilehash: 2e89df700c505eca9d1c91634e4cce8594a1d599
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347545"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a>Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)
In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen untergeordneten Elements nach dessen Namen erläutert. Wenn Sie den Namen des untergeordneten Elements kennen und wissen, dass es nur ein Element mit diesem Namen gibt, ist es möglicherweise sinnvoll, statt einer ganzen Auflistung nur ein einzelnes Element abzurufen.  
  
 Die <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gibt das erste untergeordnete <xref:System.Xml.Linq.XElement> mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.  
  
 Zum Abrufen eines einzelnen untergeordneten Elements in Visual Basic wird häufig die XML-Eigenschaft verwendet und dann das erste Element mittels der Arrayindexernotation abgerufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gezeigt. In diesem Beispiel wird die XML-Struktur mit dem Namen `po` genommen und nach dem ersten Element mit dem Namen `Comment` gesucht.  
  
 Das Visual Basic-Beispiel zeigt die Verwendung der Arrayindexernotation, um ein einzelnes Element abzurufen.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der gleiche Code für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
