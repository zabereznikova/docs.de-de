---
title: 'Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie die Werte von Elementen abrufen. Sehen Sie sich Beispiele für die Verwendung der Umwandlung von Zeichenfolgen und ganzzahligen Werten sowie der Werteigenschaft an.
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: eb750927d74c3068d7ab06caba9835110bd77a09
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301540"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a>Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)

In diesem Artikel wird das Abrufen der Werte von Elementen veranschaulicht. Es gibt zwei Hauptmethoden zum Abrufen der Werte:

- Wandeln Sie <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ um. Der explizite Konvertierungsoperator wandelt dann den Inhalt des Elements oder Attributs in den angegebenen Typ um und weist ihn Ihrer Variable zu.

- Verwenden Sie die Eigenschaft <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> oder <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>. Sie können den Wert mithilfe dieser Eigenschaften auch festlegen.

Bei C# empfiehlt sich im Allgemeinen die Umwandlung. Wenn Sie das Element oder Attribut in einen Nullable-Werttyp umwandeln, ist es einfacher, den Code zum Abrufen des Werts eines vorhandenen oder möglicherweise nicht vorhandenen Elements (oder Attributs) zu schreiben. Im [letzten Beispiel](#element-might-not-exist-example) dieses Artikels wird veranschaulicht, dass die Umwandlung in Fällen einfacher ist, in denen das Element möglicherweise nicht vorhanden ist. Während Sie bei der Verwendung der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft den Inhalt des Elements sehen können, ist dies beim Umwandeln nicht möglich.  
  
## <a name="string-cast-example"></a>Beispiel zur Umwandlung einer Zeichenfolge  
 Zum Abrufen des Werts eines Elements wandeln Sie das <xref:System.Xml.Linq.XElement>-Objekt in den gewünschten Typ um. Sie können ein Element wie folgt in eine Zeichenfolge umwandeln:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a>Beispiel zur Umwandlung eines Integers  
 Sie können Elemente auch in andere Typen als Zeichenfolgen umwandeln. Wenn Sie z. B. ein Element haben, das eine ganze Zahl enthält, können Sie das Element, wie im folgenden Code gezeigt, in den Typ `int` umwandeln:  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet explizite Umwandlungsoperatoren für die folgenden Datentypen: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] stellt dieselben Typumwandlungsoperatoren für <xref:System.Xml.Linq.XAttribute>-Objekte bereit.  
  
## <a name="value-property-example"></a>Beispiel zum Wert einer Eigenschaft  
 Zum Abrufen des Inhalts eines Elements können Sie die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwenden:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a>Beispiel zu möglicherweise nicht vorhandenen Elementen
 Es kann vorkommen, dass Sie versuchen möchten, den Wert eines Elements abzurufen, von dem Sie gar nicht genau wissen, ob es tatsächlich existiert. Wenn Sie in einem solchen Fall das umgewandelte Element einem Nullable-Verweistyp oder -Werttyp zuweisen und das Element nicht vorhanden ist, wird die zugewiesene Variable auf `null` festgelegt. Der folgende Code zeigt, dass in den Fällen, in denen nicht klar ist, ob das Element existiert oder nicht, das Arbeiten mit der Umwandlung einfacher ist als die Verwendung der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft.  
  
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
  
```output  
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

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md)
