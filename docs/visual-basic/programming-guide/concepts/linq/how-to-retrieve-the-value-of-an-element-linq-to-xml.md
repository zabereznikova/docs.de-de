---
title: 'Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
ms.openlocfilehash: cc0ddb9c4fc6364d4b10ebac378ab47cc38e508f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352426"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a>How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)
In diesem Thema wird gezeigt, wie Sie den Wert von Elementen abrufen können. Im Wesentlichen gibt es dafür zwei Möglichkeiten. Die eine Möglichkeit besteht darin, ein <xref:System.Xml.Linq.XElement> oder ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umzuwandeln. Der explizite Konvertierungsoperator wandelt dann den Inhalt des Elements oder Attributs in den angegebenen Typ um und weist ihn Ihrer Variable zu. Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft oder die <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>-Eigenschaft zu verwenden.  
  
 Wenn Sie mit Visual Basic arbeiten, empfiehlt es sich, die <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft zu verwenden.  
  
## <a name="example"></a>Beispiel  
 Zum Abrufen des Werts eines Elements wandeln Sie einfach nur das <xref:System.Xml.Linq.XElement>-Objekt in den gewünschten Typ um. Das folgende Beispiel zeigt, wie Sie ein Element in eine Zeichenfolge umwandeln können:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Beispiel  
 Sie können Elemente auch in andere Typen als Zeichenfolgen umwandeln. Wenn Sie z. B. ein Element haben, das eine ganze Zahl enthält, können Sie das Element, wie im folgenden Code gezeigt, in den Typ `int` umwandeln:  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet explizite Umwandlungsoperatoren für die folgenden Datentypen: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] stellt dieselben Typumwandlungsoperatoren für <xref:System.Xml.Linq.XAttribute>-Objekte bereit.  
  
## <a name="example"></a>Beispiel  
 Zum Abrufen des Inhalts eines Elements können Sie die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwenden:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Beispiel  
 Es kann vorkommen, dass Sie versuchen möchten, den Wert eines Elements abzurufen, von dem Sie gar nicht genau wissen, ob es tatsächlich existiert. Wenn Sie in einem solchen Fall das umgewandelte Element einem Typ zuweisen, der NULL-Werte zulässt (entweder ein `string`-Element oder einer der Typen in .NET Framework, der NULL-Werte zulässt), und das Element nicht vorhanden ist, wird die zugewiesene Variable einfach auf `Nothing` gesetzt. Der folgende Code zeigt, dass in den Fällen, in denen nicht klar ist, ob das Element existiert oder nicht, das Arbeiten mit der Umwandlung einfacher ist als die Verwendung der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft.  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```console  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 In der Regel können Sie einfacheren Code schreiben, wenn Sie zum Abrufen des Inhalts von Elementen und Attributen die Umwandlung verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
