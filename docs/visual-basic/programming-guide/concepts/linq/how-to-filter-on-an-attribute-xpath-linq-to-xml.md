---
title: 'Gewusst wie: Filtern nach einem Attribut (XPath-LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: ffefb9d6-45ec-4677-a396-dd9c2b36298f
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 321fd6aba7b8ab40b29eb0708039cb5c0f8a964d
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-filter-on-an-attribute-xpath-linq-to-xml-visual-basic"></a>Gewusst wie: Filtern nach einem Attribut (XPath-LINQ to XML) (Visual Basic)
In diesem Thema wird gezeigt, wie Sie die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.  
  
 Der XPath-Ausdruck lautet:  
  
 `.//Address[@Type='Shipping']`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht nach allen Nachfolgerelementen mit dem Namen `Address` und dem `Type`-Attribut mit dem Wert <legacyBold>"Shipping"</legacyBold>.  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: mehrere Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    From el In po...<Address> _  
    Where el.@Type = "Shipping" _  
    Select el  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    po.XPathSelectElements(".//Address[@Type='Shipping']")  
  
If (list1.Count = list2.Count And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Results are identical  
<Address Type="Shipping">  
  <Name>Ellen Adams</Name>  
  <Street>123 Maple Street</Street>  
  <City>Mill Valley</City>  
  <State>CA</State>  
  <Zip>10999</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Cristian Osorio</Name>  
  <Street>456 Main Street</Street>  
  <City>Buffalo</City>  
  <State>NY</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Jessica Arnold</Name>  
  <Street>4055 Madison Ave</Street>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML für XPath-Benutzer (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
