---
title: 'Gewusst wie: Abrufen des Werts eines Attributs (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 693746c24488029415e68a7c954143a86b7dbb16
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352400"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)
In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können. Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator. Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden. In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens. Wenn Sie das Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Attributs, von dem nicht genau bekannt ist, ob es überhaupt vorhanden ist, einfacher zu schreiben. For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
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
 Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet. For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
abcde  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
