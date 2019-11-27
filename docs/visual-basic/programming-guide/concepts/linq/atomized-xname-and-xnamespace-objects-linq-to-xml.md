---
title: Atomisierte XName- und XNamespace-Objekte (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
ms.openlocfilehash: 0ffed5d00364f6614b439480607ed521f52754ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345734"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="d24f4-102">Atomisierte XName-und XNamespace-Objekte (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d24f4-102">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="d24f4-103">Die <xref:System.Xml.Linq.XName>- und <xref:System.Xml.Linq.XNamespace>-Objekte sind *atomisiert*. Dies bedeutet, dass sie auf dasselbe Objekt verweisen, wenn sie denselben qualifizierten Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d24f4-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="d24f4-104">Dadurch wird die Leistung von Abfragen verbessert: Beim Vergleichen zweier atomisierter Namen auf Übereinstimmung muss die zugrunde liegende Intermediate Language nur ermitteln, ob die beiden Verweise auf dasselbe Objekt zeigen.</span><span class="sxs-lookup"><span data-stu-id="d24f4-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="d24f4-105">Im zugrunde liegenden Code müssen keine zeitaufwändigen Zeichenfolgenvergleiche ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d24f4-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>

## <a name="atomization-semantics"></a><span data-ttu-id="d24f4-106">Atomisierungssemantik</span><span class="sxs-lookup"><span data-stu-id="d24f4-106">Atomization Semantics</span></span>

<span data-ttu-id="d24f4-107">Atomisierung bedeutet, dass zwei <xref:System.Xml.Linq.XName>-Objekte dieselbe Instanz gemeinsam nutzen, wenn sie über denselben lokalen Namen verfügen und sich im selben Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="d24f4-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="d24f4-108">Dementsprechend nutzen zwei <xref:System.Xml.Linq.XNamespace>-Objekte dieselbe Instanz gemeinsam, wenn sie über denselben Namespace-URI verfügen.</span><span class="sxs-lookup"><span data-stu-id="d24f4-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>

<span data-ttu-id="d24f4-109">Damit eine Klasse atomisierte Objekte unterstützt, muss der Konstruktor für die Klasse privat sein, nicht öffentlich.</span><span class="sxs-lookup"><span data-stu-id="d24f4-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="d24f4-110">Bei einem öffentlichen Konstruktor könnten Sie ein nicht atomisiertes Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="d24f4-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="d24f4-111">Die <xref:System.Xml.Linq.XName>-Klasse und die <xref:System.Xml.Linq.XNamespace>-Klasse implementieren einen impliziten Konvertierungsoperator, um eine Zeichenfolge in einen <xref:System.Xml.Linq.XName> oder einen <xref:System.Xml.Linq.XNamespace> zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d24f4-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="d24f4-112">Auf diese Weise können Sie eine Instanz dieser Objekte abrufen.</span><span class="sxs-lookup"><span data-stu-id="d24f4-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="d24f4-113">Sie können keine Instanz über einen Konstruktor abrufen, da Sie auf den Konstruktor nicht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d24f4-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>

<span data-ttu-id="d24f4-114"><xref:System.Xml.Linq.XName> und <xref:System.Xml.Linq.XNamespace> implementieren auch die Gleichheits-und Ungleichheits Operatoren, um zu bestimmen, ob die beiden verglichenen Objekte Verweise auf dieselbe Instanz sind.</span><span class="sxs-lookup"><span data-stu-id="d24f4-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>

## <a name="example"></a><span data-ttu-id="d24f4-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d24f4-115">Example</span></span>

<span data-ttu-id="d24f4-116">Im folgenden Code werden mehrere <xref:System.Xml.Linq.XElement>-Objekte erstellt, und es wird veranschaulicht, dass identische Namen dieselbe Instanz aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d24f4-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

<span data-ttu-id="d24f4-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d24f4-117">This example produces the following output:</span></span>

```console
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

<span data-ttu-id="d24f4-118">Wie bereits erwähnt, besteht der Vorteil atomisierter Objekte darin, dass beim Verwenden einer der Achsenmethoden, die als Parameter einen <xref:System.Xml.Linq.XName> erfordert, zum Auswählen der gewünschten Elemente nur ermittelt werden muss, ob die beiden Namen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="d24f4-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>

<span data-ttu-id="d24f4-119">Im folgenden Beispiel wird ein <xref:System.Xml.Linq.XName> an den <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methodenaufruf übergeben. Dieser erreicht aufgrund des Atomarisierungsmusters eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="d24f4-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

<span data-ttu-id="d24f4-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d24f4-120">This example produces the following output:</span></span>

```xml
<C1>1</C1>
<C1>1</C1>
```

## <a name="see-also"></a><span data-ttu-id="d24f4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d24f4-121">See also</span></span>

- [<span data-ttu-id="d24f4-122">Leistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d24f4-122">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
