---
title: 'Gewusst wie: Suchen eines untergeordneten Elements (XPath-LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b54bc8a2b7821399857f716c35a651c24de10f3f
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a>Gewusst wie: Suchen eines untergeordneten Elements (XPath-LINQ to XML) (Visual Basic)
In diesem Thema vergleicht die Achse der untergeordneten XPath-Element mit dem [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>-Methode.</xref:System.Xml.Linq.XContainer.Element%2A>  
  
 Der XPath-Ausdruck lautet `DeliveryNotes`.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ermittelt das untergeordnete Element `DeliveryNotes`.  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: mehrere Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML für XPath-Benutzer (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
