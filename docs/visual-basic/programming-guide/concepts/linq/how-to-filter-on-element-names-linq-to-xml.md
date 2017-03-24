---
title: 'Gewusst wie: Filtern nach Elementnamen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 07f7867b0fc5cf79ba5ce06f95b07b5c538e83d3
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a>Gewusst wie: Filtern nach Elementnamen (LINQ to XML) (Visual Basic)
Beim Aufruf einer der Methoden, die zurückgeben <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>, Sie können Filtern nach Elementnamen vornehmen.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Auflistung mit Nachfolgerelementen abgerufen, die gefiltert wird, damit sie nur die Nachfolgerelemente mit dem angegebenen Namen enthält.  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Dieser Code erzeugt die folgende Ausgabe:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Die anderen Methoden, die zurückgeben <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>Sammlungen folgen demselben Muster.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Ihre Signaturen entsprechen und <xref:System.Xml.Linq.XContainer.Elements%2A> <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A> Im Folgenden finden Sie eine vollständige Liste der Methoden, die gleiche Methodensignaturen besitzen:  
  
-   <xref:System.Xml.Linq.XNode.Ancestors%2A></xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
