---
title: 'Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie den Werte eines Attributs abrufen. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 5ee6995a54829b6d992e2982e6a6effcabf76470
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301553"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="3f743-104">Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3f743-104">How to retrieve the value of an attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="3f743-105">In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="3f743-105">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="3f743-106">Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="3f743-106">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="3f743-107">Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f743-107">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="3f743-108">In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens.</span><span class="sxs-lookup"><span data-stu-id="3f743-108">However, casting is generally the better approach.</span></span> <span data-ttu-id="3f743-109">Wenn Sie das Attribut in einen Nullable-Werttyp umwandeln, ist es einfacher, den Code zum Abrufen des Werts eines vorhandenen oder möglicherweise nicht vorhandenen Attributs zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3f743-109">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="3f743-110">Beispiele für dieses Verfahren finden Sie unter [Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3f743-110">For examples of this technique, see [How to retrieve the value of an element (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f743-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f743-111">Example</span></span>  
 <span data-ttu-id="3f743-112">Zum Abrufen des Werts eines Attributs wandeln Sie einfach nur das <xref:System.Xml.Linq.XAttribute>-Objekt in den gewünschten Typ um.</span><span class="sxs-lookup"><span data-stu-id="3f743-112">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="3f743-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3f743-113">This example produces the following output:</span></span>  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="3f743-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f743-114">Example</span></span>  
 <span data-ttu-id="3f743-115">Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="3f743-115">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="3f743-116">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3f743-116">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="3f743-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3f743-117">This example produces the following output:</span></span>  
  
```output  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f743-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f743-118">See also</span></span>

- [<span data-ttu-id="3f743-119">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="3f743-119">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
