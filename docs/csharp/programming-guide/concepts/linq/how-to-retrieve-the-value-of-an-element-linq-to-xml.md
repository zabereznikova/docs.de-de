---
title: 'Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: 6f2d355eac9914cd4c03d3a4521992b346b92f0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168686"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="79419-102">Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="79419-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="79419-103">In diesem Thema wird gezeigt, wie Sie den Wert von Elementen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="79419-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="79419-104">Im Wesentlichen gibt es dafür zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="79419-104">There are two main ways to do this.</span></span> <span data-ttu-id="79419-105">Die eine Möglichkeit besteht darin, ein <xref:System.Xml.Linq.XElement> oder ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="79419-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="79419-106">Der explizite Konvertierungsoperator wandelt dann den Inhalt des Elements oder Attributs in den angegebenen Typ um und weist ihn Ihrer Variable zu.</span><span class="sxs-lookup"><span data-stu-id="79419-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="79419-107">Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft oder die <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>-Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="79419-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="79419-108">Bei Verwendung von C# ist die Umwandlung aber in der Regel der bessere Ansatz.</span><span class="sxs-lookup"><span data-stu-id="79419-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="79419-109">Wenn Sie das Element oder Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Elements (oder Attributs), das vorhanden oder nicht vorhanden ist, einfacher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="79419-109">If you cast the element or attribute to a nullable type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="79419-110">Dies wird im letzten Beispiel in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="79419-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="79419-111">Während Sie bei der Verwendung der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft den Inhalt des Elements sehen können, ist dies beim Umwandeln nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="79419-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79419-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79419-112">Example</span></span>  
 <span data-ttu-id="79419-113">Zum Abrufen des Werts eines Elements wandeln Sie einfach nur das <xref:System.Xml.Linq.XElement>-Objekt in den gewünschten Typ um.</span><span class="sxs-lookup"><span data-stu-id="79419-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="79419-114">Das folgende Beispiel zeigt, wie Sie ein Element in eine Zeichenfolge umwandeln können:</span><span class="sxs-lookup"><span data-stu-id="79419-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="79419-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79419-115">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="79419-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79419-116">Example</span></span>  
 <span data-ttu-id="79419-117">Sie können Elemente auch in andere Typen als Zeichenfolgen umwandeln.</span><span class="sxs-lookup"><span data-stu-id="79419-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="79419-118">Wenn Sie z. B. ein Element haben, das eine ganze Zahl enthält, können Sie das Element, wie im folgenden Code gezeigt, in den Typ `int` umwandeln:</span><span class="sxs-lookup"><span data-stu-id="79419-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="79419-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79419-119">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="79419-120">bietet explizite Umwandlungsoperatoren für die folgenden Datentypen: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="79419-120">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="79419-121">stellt dieselben Typumwandlungsoperatoren für <xref:System.Xml.Linq.XAttribute>-Objekte bereit.</span><span class="sxs-lookup"><span data-stu-id="79419-121">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79419-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79419-122">Example</span></span>  
 <span data-ttu-id="79419-123">Zum Abrufen des Inhalts eines Elements können Sie die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwenden:</span><span class="sxs-lookup"><span data-stu-id="79419-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="79419-124">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79419-124">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="79419-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79419-125">Example</span></span>  
 <span data-ttu-id="79419-126">Es kann vorkommen, dass Sie versuchen möchten, den Wert eines Elements abzurufen, von dem Sie gar nicht genau wissen, ob es tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="79419-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="79419-127">Wenn Sie in einem solchen Fall das umgewandelte Element einem Typ zuweisen, der NULL-Werte zulässt (entweder ein `string`-Element oder einer der Typen in .NET Framework, der NULL-Werte zulässt), und das Element nicht vorhanden ist, wird die zugewiesene Variable einfach auf `null` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="79419-127">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the .NET Framework), if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="79419-128">Der folgende Code zeigt, dass in den Fällen, in denen nicht klar ist, ob das Element existiert oder nicht, das Arbeiten mit der Umwandlung einfacher ist als die Verwendung der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="79419-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="79419-129">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79419-129">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="79419-130">In der Regel können Sie einfacheren Code schreiben, wenn Sie zum Abrufen des Inhalts von Elementen und Attributen die Umwandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="79419-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79419-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79419-131">See also</span></span>

- [<span data-ttu-id="79419-132">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="79419-132">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
