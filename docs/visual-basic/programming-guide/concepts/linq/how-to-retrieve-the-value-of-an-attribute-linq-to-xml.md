---
title: 'Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6593639dcdc234ddda808cfdb5e85ebe1a771b62
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248946"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>Gewusst wie: Abrufen des Werts eines Attributs (LINQ zu XML) (Visual Basic)
In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können. Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator. Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden. In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens. Wenn Sie das Attribut in einen NULL-Werttyp umlegen, ist der Code einfacher zu schreiben, wenn der Wert eines Attributs abgerufen wird, das möglicherweise nicht vorhanden ist. Beispiele für diese Technik finden Sie unter [Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Beispiel  
 In Visual Basic können Sie zum Abrufen des Werts eines Attributs die integrierte Attributeigenschaft verwenden.  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Beispiel  
 In Visual Basic können Sie zum Festlegen des Werts eines Attributs die integrierte Attributeigenschaft verwenden. Wenn Sie die integrierte Attributeigenschaft verwenden und den Wert eines Attributs festlegen, das nicht existiert, wird dieses Attribut erstellt.  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet. Weitere Informationen finden Sie unter [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
```console  
abcde  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
