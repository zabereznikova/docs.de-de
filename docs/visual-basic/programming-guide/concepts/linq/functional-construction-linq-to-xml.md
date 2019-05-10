---
title: Funktionale Konstruktion (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
ms.openlocfilehash: a942d4a0fa4c33cf4699c5825ea05403bdfce48f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64618321"
---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>Funktionale Konstruktion (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet mit der *funktionalen Konstruktion* eine leistungsfähige Möglichkeit zur Erstellung von XML-Elementen. Funktionale Konstruktion ist die Fähigkeit, eine XML-Struktur in einer einzelnen Anweisung zu erstellen.  
  
 Es gibt mehrere wichtige Features der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Programmierschnittstelle, die für die funktionale Konstruktion verantwortlich sind:  
  
- Der <xref:System.Xml.Linq.XElement>-Konstruktor akzeptiert verschiedene Argumentarten als Inhalt. So können Sie z. B. ein anderes <xref:System.Xml.Linq.XElement>-Objekt übergeben, das zu einem untergeordneten Element wird. Sie können auch ein <xref:System.Xml.Linq.XAttribute>-Objekt übergeben, das zu einem Attribut des Elements wird. Oder Sie übergeben ein beliebiges anderes Objekt, das in eine Zeichenfolge konvertiert wird und zum Textinhalt des Elements wird.  
  
- Der <xref:System.Xml.Linq.XElement>-Konstruktor verwendet ein `params`-Array vom Typ <xref:System.Object>, sodass Sie beliebig viele Objekte an den Konstruktor übergeben können. Auf diese Weise können Sie ein Element erstellen, das über komplexen Inhalt verfügt.  
  
- Wenn ein Objekt eine <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung werden hinzugefügt. Wenn die Auflistung <xref:System.Xml.Linq.XElement>-Objekte oder <xref:System.Xml.Linq.XAttribute>-Objekte enthält, wird jedes Element in der Auflistung getrennt hinzugefügt. Dies ist wichtig, da Sie auf diese Weise die Ergebnisse einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage an den Konstruktor übergeben können.  
  
 Im Folgenden finden Sie ein Beispiel dazu:  
  
 Diese Funktionen ermöglichen es Ihnen, zum Schreiben von Code mit XML-Literalen aus, um eine XML-Struktur zu erstellen und auch Code schreiben, verwendet die Ergebnisse der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen, bei der Erstellung einer XML-Struktur:  
  
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

- [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
