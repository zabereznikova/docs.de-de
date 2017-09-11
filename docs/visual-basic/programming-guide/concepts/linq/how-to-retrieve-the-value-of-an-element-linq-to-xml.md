---
title: 'Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: be5eebc382f83819fd978554f830b6ba12227902
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a><span data-ttu-id="cbb9a-102">Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbb9a-102">How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="cbb9a-103">In diesem Thema wird gezeigt, wie Sie den Wert von Elementen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="cbb9a-104">Im Wesentlichen gibt es dafür zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-104">There are two main ways to do this.</span></span> <span data-ttu-id="cbb9a-105">Eine Möglichkeit ist die Umwandlung einer <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>in den gewünschten Typ.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="cbb9a-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="cbb9a-106">Der explizite Konvertierungsoperator wandelt dann den Inhalt des Elements oder Attributs in den angegebenen Typ um und weist ihn Ihrer Variable zu.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="cbb9a-107">Alternativ können Sie die <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>Eigenschaft oder die <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>Eigenschaft.</xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="cbb9a-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> property.</span></span>  
  
 <span data-ttu-id="cbb9a-108">In Visual Basic der beste Ansatz ist die Verwendung der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>Eigenschaft.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="cbb9a-108">With Visual Basic, the best approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbb9a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbb9a-109">Example</span></span>  
 <span data-ttu-id="cbb9a-110">Zum Abrufen des Werts eines Elements wandeln Sie einfach nur die <xref:System.Xml.Linq.XElement>Objekt in den gewünschten Typ.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="cbb9a-110">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="cbb9a-111">Das folgende Beispiel zeigt, wie Sie ein Element in eine Zeichenfolge umwandeln können:</span><span class="sxs-lookup"><span data-stu-id="cbb9a-111">You can always cast an element to a string, as follows:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="cbb9a-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cbb9a-112">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="cbb9a-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbb9a-113">Example</span></span>  
 <span data-ttu-id="cbb9a-114">Sie können Elemente auch in andere Typen als Zeichenfolgen umwandeln.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-114">You can also cast elements to types other than string.</span></span> <span data-ttu-id="cbb9a-115">Wenn Sie z. B. ein Element haben, das eine ganze Zahl enthält, können Sie das Element, wie im folgenden Code gezeigt, in den Typ `int` umwandeln:</span><span class="sxs-lookup"><span data-stu-id="cbb9a-115">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 <span data-ttu-id="cbb9a-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cbb9a-116">This example produces the following output:</span></span>  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="cbb9a-117">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-117"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="cbb9a-118">stellt dieselben Typumwandlungsoperatoren für <xref:System.Xml.Linq.XAttribute>Objekte.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="cbb9a-118"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbb9a-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbb9a-119">Example</span></span>  
 <span data-ttu-id="cbb9a-120">Sie können die <xref:System.Xml.Linq.XElement.Value%2A>Eigenschaft zum Abrufen des Inhalts eines Elements:</xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="cbb9a-120">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="cbb9a-121">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cbb9a-121">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="cbb9a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbb9a-122">Example</span></span>  
 <span data-ttu-id="cbb9a-123">Es kann vorkommen, dass Sie versuchen möchten, den Wert eines Elements abzurufen, von dem Sie gar nicht genau wissen, ob es tatsächlich existiert.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-123">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="cbb9a-124">In diesem Fall Wenn Sie zuweisen das umgewandelte Element einem auf NULL festlegbaren Typ (entweder `string` oder eine auf NULL festlegbare Typen in der [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), wenn das Element nicht die zugewiesene existiert Variable einfach auf festgelegt ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-124">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), if the element does not exist the assigned variable is just set to `Nothing`.</span></span> <span data-ttu-id="cbb9a-125">Der folgende Code zeigt, dass das Element möglicherweise oder ist nicht vorhanden, mit der Umwandlung als die Verwendung einfacher ist es die <xref:System.Xml.Linq.XElement.Value%2A>Eigenschaft.</xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="cbb9a-125">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="cbb9a-126">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cbb9a-126">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="cbb9a-127">In der Regel können Sie einfacheren Code schreiben, wenn Sie zum Abrufen des Inhalts von Elementen und Attributen die Umwandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbb9a-127">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb9a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbb9a-128">See Also</span></span>  
 [<span data-ttu-id="cbb9a-129">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbb9a-129">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
