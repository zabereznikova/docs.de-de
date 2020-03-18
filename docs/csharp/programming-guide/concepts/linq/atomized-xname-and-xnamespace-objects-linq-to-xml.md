---
title: Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: bc5066440d87f5485ae9099d7a7f4f5e9e66b4ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204271"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a><span data-ttu-id="23fc4-102">Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="23fc4-102">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="23fc4-103">Die <xref:System.Xml.Linq.XName>- und <xref:System.Xml.Linq.XNamespace>-Objekte sind *atomisiert*. Dies bedeutet, dass sie auf dasselbe Objekt verweisen, wenn sie denselben qualifizierten Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="23fc4-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="23fc4-104">Dadurch wird die Leistung von Abfragen verbessert: Beim Vergleichen zweier atomisierter Namen auf Übereinstimmung muss die zugrunde liegende Intermediate Language nur ermitteln, ob die beiden Verweise auf dasselbe Objekt zeigen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="23fc4-105">Im zugrunde liegenden Code müssen keine zeitaufwändigen Zeichenfolgenvergleiche ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23fc4-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="23fc4-106">Atomisierungssemantik</span><span class="sxs-lookup"><span data-stu-id="23fc4-106">Atomization Semantics</span></span>  
 <span data-ttu-id="23fc4-107">Atomisierung bedeutet, dass zwei <xref:System.Xml.Linq.XName>-Objekte dieselbe Instanz gemeinsam nutzen, wenn sie über denselben lokalen Namen verfügen und sich im selben Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="23fc4-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="23fc4-108">Dementsprechend nutzen zwei <xref:System.Xml.Linq.XNamespace>-Objekte dieselbe Instanz gemeinsam, wenn sie über denselben Namespace-URI verfügen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="23fc4-109">Damit eine Klasse atomisierte Objekte unterstützt, muss der Konstruktor für die Klasse privat sein, nicht öffentlich.</span><span class="sxs-lookup"><span data-stu-id="23fc4-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="23fc4-110">Bei einem öffentlichen Konstruktor könnten Sie ein nicht atomisiertes Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="23fc4-111">Die <xref:System.Xml.Linq.XName>-Klasse und die <xref:System.Xml.Linq.XNamespace>-Klasse implementieren einen impliziten Konvertierungsoperator, um eine Zeichenfolge in einen <xref:System.Xml.Linq.XName> oder einen <xref:System.Xml.Linq.XNamespace> zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="23fc4-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="23fc4-112">Auf diese Weise können Sie eine Instanz dieser Objekte abrufen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="23fc4-113">Sie können keine Instanz über einen Konstruktor abrufen, da Sie auf den Konstruktor nicht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="23fc4-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="23fc4-114">Außerdem werden von <xref:System.Xml.Linq.XName> und <xref:System.Xml.Linq.XNamespace> Gleichheits- und Ungleichheitsoperatoren implementiert, mit denen Sie ermitteln können, ob die beiden verglichenen Objekte Verweise auf dieselbe Instanz darstellen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23fc4-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23fc4-115">Example</span></span>  
 <span data-ttu-id="23fc4-116">Im folgenden Code werden mehrere <xref:System.Xml.Linq.XElement>-Objekte erstellt, und es wird veranschaulicht, dass identische Namen dieselbe Instanz aufweisen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 <span data-ttu-id="23fc4-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23fc4-117">This example produces the following output:</span></span>  
  
```output  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="23fc4-118">Wie bereits erwähnt, besteht der Vorteil atomisierter Objekte darin, dass beim Verwenden einer der Achsenmethoden, die als Parameter einen <xref:System.Xml.Linq.XName> erfordert, zum Auswählen der gewünschten Elemente nur ermittelt werden muss, ob die beiden Namen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="23fc4-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="23fc4-119">Im folgenden Beispiel wird ein <xref:System.Xml.Linq.XName> an den <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methodenaufruf übergeben. Dieser erreicht aufgrund des Atomarisierungsmusters eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="23fc4-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 <span data-ttu-id="23fc4-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23fc4-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
