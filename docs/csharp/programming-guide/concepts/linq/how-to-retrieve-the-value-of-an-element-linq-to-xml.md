---
title: 'Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a3f844917ff1d9841c1c6f7f727f593868ec43b8
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a>Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)
In diesem Thema wird gezeigt, wie Sie den Wert von Elementen abrufen können. Im Wesentlichen gibt es dafür zwei Möglichkeiten. Die erste Möglichkeit ist die Umwandlung eines <xref:System.Xml.Linq.XElement> oder eines <xref:System.Xml.Linq.XAttribute> in einen gewünschten Typen. Der explizite Konvertierungsoperator wandelt dann den Inhalt des Elements oder Attributs in den angegebenen Typ um und weist ihn Ihrer Variable zu. Die zweite Möglichkeit ist der Einsatz der Eigenschaften <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> oder <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>.  
  
 Bei Verwendung von C# ist die Umwandlung aber in der Regel der bessere Ansatz. Wenn Sie das Element oder Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Elements (oder Attributs), das vorhanden oder nicht vorhanden ist, einfacher zu schreiben. Dies wird im letzten Beispiel in diesem Thema gezeigt. Sie können allerdings die Inhalte eines Elements nicht durch die Umwandlung festlegen, so wie Sie es mit der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>-Eigenschaft können.  
  
## <a name="example"></a>Beispiel  
 Zum Abrufen des Werts eines Elements wandeln Sie einfach nur das <xref:System.Xml.Linq.XElement>-Objekt in den gewünschten Typ um. Das folgende Beispiel zeigt, wie Sie ein Element in eine Zeichenfolge umwandeln können:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Beispiel  
 Sie können Elemente auch in andere Typen als Zeichenfolgen umwandeln. Wenn Sie z. B. ein Element haben, das eine ganze Zahl enthält, können Sie das Element, wie im folgenden Code gezeigt, in den Typ `int` umwandeln:  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bietet explizite Umwandlungsoperatoren für die folgenden Datentypen: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bietet dieselben Umwandlungsoperatoren für <xref:System.Xml.Linq.XAttribute>-Objekte.  
  
## <a name="example"></a>Beispiel  
 Sie können die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwenden, um Inhalte eines Elements abzurufen:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");   
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Beispiel  
 Es kann vorkommen, dass Sie versuchen möchten, den Wert eines Elements abzurufen, von dem Sie gar nicht genau wissen, ob es tatsächlich existiert. Wenn Sie in einem solchen Fall das umgewandelte Element einem Typ zuweisen, der NULL-Werte zulässt (entweder eine `string` oder einer der Typen in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], der NULL-Werte zulässt) und wenn das Element nicht existiert, wird die zugewiesene Variable einfach auf `null` gesetzt. Der folgende Code zeigt, dass in den Fällen, in denen nicht klar ist, ob das Element existiert oder nicht, das Arbeiten mit der Umwandlung einfacher ist als die Verwendung der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
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
 [LINQ to XML-Achsen (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
