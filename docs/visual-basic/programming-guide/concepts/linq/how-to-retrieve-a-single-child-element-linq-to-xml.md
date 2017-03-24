---
title: 'Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9e96e2e2270f16364b0a26a0b4f17c0d96d7c38b
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a>Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)
In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen untergeordneten Elements nach dessen Namen erläutert. Wenn Sie den Namen des untergeordneten Elements kennen und wissen, dass es nur ein Element mit diesem Namen gibt, ist es möglicherweise sinnvoll, statt einer ganzen Auflistung nur ein einzelnes Element abzurufen.  
  
 Die <xref:System.Xml.Linq.XContainer.Element%2A>Methode gibt die untergeordneten-erste <xref:System.Xml.Linq.XElement>mit der angegebenen <xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> zurück</xref:System.Xml.Linq.XContainer.Element%2A>  
  
 Zum Abrufen eines einzelnen untergeordneten Elements in Visual Basic wird häufig die XML-Eigenschaft verwendet und dann das erste Element mittels der Arrayindexernotation abgerufen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode.</xref:System.Xml.Linq.XContainer.Element%2A> In diesem Beispiel wird die XML-Struktur mit dem Namen `po` genommen und nach dem ersten Element mit dem Namen `Comment` gesucht.  
  
 Das Visual Basic-Beispiel zeigt die Verwendung der Arrayindexernotation, um ein einzelnes Element abzurufen.  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
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
 Im folgenden Beispiel wird der gleiche Code für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
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
 [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
