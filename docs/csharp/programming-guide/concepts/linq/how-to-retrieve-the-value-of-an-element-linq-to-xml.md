---
title: 'Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: c4bb78e937fe0de08242923cdd7cd638abf571c7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805834"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="3773f-102">Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3773f-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>

<span data-ttu-id="3773f-103">In diesem Artikel wird das Abrufen der Werte von Elementen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3773f-103">This article shows how to get the value of elements.</span></span> <span data-ttu-id="3773f-104">Es gibt zwei Hauptmethoden zum Abrufen der Werte:</span><span class="sxs-lookup"><span data-stu-id="3773f-104">There are two main ways to get the value:</span></span>

- <span data-ttu-id="3773f-105">Wandeln Sie <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ um.</span><span class="sxs-lookup"><span data-stu-id="3773f-105">Cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="3773f-106">Der explizite Konvertierungsoperator wandelt dann den Inhalt des Elements oder Attributs in den angegebenen Typ um und weist ihn Ihrer Variable zu.</span><span class="sxs-lookup"><span data-stu-id="3773f-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span>

- <span data-ttu-id="3773f-107">Verwenden Sie die Eigenschaft <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> oder <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3773f-107">Use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> or <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="3773f-108">Sie können den Wert mithilfe dieser Eigenschaften auch festlegen.</span><span class="sxs-lookup"><span data-stu-id="3773f-108">You can also set the value using these properties.</span></span>

<span data-ttu-id="3773f-109">Bei C# empfiehlt sich im Allgemeinen die Umwandlung.</span><span class="sxs-lookup"><span data-stu-id="3773f-109">With C#, casting is generally the better approach.</span></span> <span data-ttu-id="3773f-110">Wenn Sie das Element oder Attribut in einen Nullable-Werttyp umwandeln, ist es einfacher, den Code zum Abrufen des Werts eines vorhandenen oder möglicherweise nicht vorhandenen Elements (oder Attributs) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3773f-110">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="3773f-111">Im [letzten Beispiel](#element-might-not-exist-example) dieses Artikels wird veranschaulicht, dass die Umwandlung in Fällen einfacher ist, in denen das Element möglicherweise nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3773f-111">The [last example](#element-might-not-exist-example) in this article demonstrates that casting is simpler in the case where the element might not exist.</span></span> <span data-ttu-id="3773f-112">Während Sie bei der Verwendung der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft den Inhalt des Elements sehen können, ist dies beim Umwandeln nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="3773f-112">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="string-cast-example"></a><span data-ttu-id="3773f-113">Beispiel zur Umwandlung einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3773f-113">String cast example</span></span>  
 <span data-ttu-id="3773f-114">Zum Abrufen des Werts eines Elements wandeln Sie das <xref:System.Xml.Linq.XElement>-Objekt in den gewünschten Typ um.</span><span class="sxs-lookup"><span data-stu-id="3773f-114">To retrieve the value of an element, cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="3773f-115">Sie können ein Element wie folgt in eine Zeichenfolge umwandeln:</span><span class="sxs-lookup"><span data-stu-id="3773f-115">You can cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="3773f-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3773f-116">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a><span data-ttu-id="3773f-117">Beispiel zur Umwandlung eines Integers</span><span class="sxs-lookup"><span data-stu-id="3773f-117">Integer cast example</span></span>  
 <span data-ttu-id="3773f-118">Sie können Elemente auch in andere Typen als Zeichenfolgen umwandeln.</span><span class="sxs-lookup"><span data-stu-id="3773f-118">You can also cast elements to types other than string.</span></span> <span data-ttu-id="3773f-119">Wenn Sie z. B. ein Element haben, das eine ganze Zahl enthält, können Sie das Element, wie im folgenden Code gezeigt, in den Typ `int` umwandeln:</span><span class="sxs-lookup"><span data-stu-id="3773f-119">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="3773f-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3773f-120">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3773f-121">bietet explizite Umwandlungsoperatoren für die folgenden Datentypen: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="3773f-121">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3773f-122">stellt dieselben Typumwandlungsoperatoren für <xref:System.Xml.Linq.XAttribute>-Objekte bereit.</span><span class="sxs-lookup"><span data-stu-id="3773f-122">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="value-property-example"></a><span data-ttu-id="3773f-123">Beispiel zum Wert einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3773f-123">Value property example</span></span>  
 <span data-ttu-id="3773f-124">Zum Abrufen des Inhalts eines Elements können Sie die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwenden:</span><span class="sxs-lookup"><span data-stu-id="3773f-124">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="3773f-125">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3773f-125">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a><span data-ttu-id="3773f-126">Beispiel zu möglicherweise nicht vorhandenen Elementen</span><span class="sxs-lookup"><span data-stu-id="3773f-126">Element might not exist example</span></span>
 <span data-ttu-id="3773f-127">Es kann vorkommen, dass Sie versuchen möchten, den Wert eines Elements abzurufen, von dem Sie gar nicht genau wissen, ob es tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="3773f-127">Sometimes you try to retrieve the value of an element even though you're not sure if it exists.</span></span> <span data-ttu-id="3773f-128">Wenn Sie in einem solchen Fall das umgewandelte Element einem Nullable-Verweistyp oder -Werttyp zuweisen und das Element nicht vorhanden ist, wird die zugewiesene Variable auf `null` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3773f-128">In this case, when you assign the casted element to a nullable reference type or nullable value type, if the element does not exist, the assigned variable is set to `null`.</span></span> <span data-ttu-id="3773f-129">Der folgende Code zeigt, dass in den Fällen, in denen nicht klar ist, ob das Element existiert oder nicht, das Arbeiten mit der Umwandlung einfacher ist als die Verwendung der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3773f-129">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="3773f-130">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3773f-130">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="3773f-131">In der Regel können Sie einfacheren Code schreiben, wenn Sie zum Abrufen des Inhalts von Elementen und Attributen die Umwandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3773f-131">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3773f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3773f-132">See also</span></span>

- [<span data-ttu-id="3773f-133">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="3773f-133">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
