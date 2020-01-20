---
title: 'Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: d5b8bb3b5857b82a61367953b8e1cd63bea90beb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347435"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="c44e0-102">Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c44e0-102">How to retrieve the value of an attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="c44e0-103">In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="c44e0-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="c44e0-104">Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="c44e0-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="c44e0-105">Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c44e0-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="c44e0-106">In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens.</span><span class="sxs-lookup"><span data-stu-id="c44e0-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="c44e0-107">Wenn Sie das Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Attributs, von dem nicht genau bekannt ist, ob es überhaupt vorhanden ist, einfacher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c44e0-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="c44e0-108">Beispiele für dieses Verfahren finden Sie unter [Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c44e0-108">For examples of this technique, see [How to retrieve the value of an element (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c44e0-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c44e0-109">Example</span></span>  
 <span data-ttu-id="c44e0-110">Zum Abrufen des Werts eines Attributs wandeln Sie einfach nur das <xref:System.Xml.Linq.XAttribute>-Objekt in den gewünschten Typ um.</span><span class="sxs-lookup"><span data-stu-id="c44e0-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="c44e0-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c44e0-111">This example produces the following output:</span></span>  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="c44e0-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c44e0-112">Example</span></span>  
 <span data-ttu-id="c44e0-113">Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="c44e0-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="c44e0-114">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c44e0-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="c44e0-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c44e0-115">This example produces the following output:</span></span>  
  
```output  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="c44e0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c44e0-116">See also</span></span>

- [<span data-ttu-id="c44e0-117">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="c44e0-117">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
