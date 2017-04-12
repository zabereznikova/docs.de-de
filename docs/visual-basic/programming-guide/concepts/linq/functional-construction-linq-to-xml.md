---
title: Funktionale Konstruktion (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fa8cb3c97a1e23a863296c828c82b240e9ab5db
ms.lasthandoff: 03/13/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>Funktionale Konstruktion (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]bietet eine leistungsfähige Möglichkeit zur Erstellung von XML-Elementen *funktionale Konstruktion*. Funktionale Konstruktion ist die Fähigkeit, eine XML-Struktur in einer einzelnen Anweisung zu erstellen.  
  
 Es gibt mehrere wichtige Features der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Programmierschnittstelle, die für die funktionale Konstruktion verantwortlich sind:  
  
-   Die <xref:System.Xml.Linq.XElement>Konstruktor akzeptiert verschiedene Argumentarten als Inhalt.</xref:System.Xml.Linq.XElement> Sie können z. B. übergeben einer anderen <xref:System.Xml.Linq.XElement>-Objekt, das ein untergeordnetes Element wird.</xref:System.Xml.Linq.XElement> Sie können übergeben ein <xref:System.Xml.Linq.XAttribute>-Objekt, das ein Attribut des Elements wird.</xref:System.Xml.Linq.XAttribute> Oder Sie übergeben ein beliebiges anderes Objekt, das in eine Zeichenfolge konvertiert wird und zum Textinhalt des Elements wird.  
  
-   Die <xref:System.Xml.Linq.XElement>Konstruktor akzeptiert ein `params` Array vom Typ <xref:System.Object>, sodass Sie beliebig viele Objekte an den Konstruktor übergeben können.</xref:System.Object> </xref:System.Xml.Linq.XElement> Auf diese Weise können Sie ein Element erstellen, das über komplexen Inhalt verfügt.  
  
-   Wenn ein Objekt implementiert <xref:System.Collections.Generic.IEnumerable%601>, die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung hinzugefügt werden.</xref:System.Collections.Generic.IEnumerable%601> Wenn die Auflistung enthält <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte, die jedes Element in der Auflistung getrennt hinzugefügt.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Dies ist wichtig, da Sie die Übergabe der Ergebnisse von können eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage an den Konstruktor.  
  
 Im Folgenden finden Sie ein Beispiel dazu:  
  
 Diese Funktionen ermöglichen Ihnen das Schreiben von Code mit XML-Literalen, um eine XML-Struktur zu erstellen und Code schreiben, der die Ergebnisse der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen, wenn Sie eine XML-Struktur erstellen:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
