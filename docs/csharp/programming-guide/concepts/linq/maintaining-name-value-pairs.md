---
title: Warten von Name-Wert-Paaren (C#)
description: LINQ to XML enthält Methoden, die das Verwalten von Name-Wert-Paaren entweder als Attribute oder als mehrere untergeordnete Elemente vereinfacht.
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 92a45d160cbb1ef470d93bf740d0b6f584681e72
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165270"
---
# <a name="maintaining-namevalue-pairs-c"></a><span data-ttu-id="70865-103">Warten von Name/Wert-Paaren (C#)</span><span class="sxs-lookup"><span data-stu-id="70865-103">Maintaining Name/Value Pairs (C#)</span></span>
<span data-ttu-id="70865-104">Viele Anwendungen müssen Informationen verwalten, die am besten als Name/Wert-Paare geführt werden.</span><span class="sxs-lookup"><span data-stu-id="70865-104">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="70865-105">Solche Informationen können z. B. Konfigurationsinformationen oder globale Einstellungen sein.</span><span class="sxs-lookup"><span data-stu-id="70865-105">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="70865-106">enthält einige Methoden, die das Unterhalten von Name/Wert-Paaren vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="70865-106">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="70865-107">Sie können die Informationen entweder als Attribute oder als Satz untergeordneter Elemente unterhalten.</span><span class="sxs-lookup"><span data-stu-id="70865-107">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="70865-108">Ein Unterschied zwischen diesen beiden Formen besteht darin, dass Attribute der Beschränkung unterliegen, dass pro Element immer nur ein Attribut mit einem bestimmten Namen vorhanden sein darf.</span><span class="sxs-lookup"><span data-stu-id="70865-108">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="70865-109">Für untergeordnete Elemente gilt diese Einschränkung nicht.</span><span class="sxs-lookup"><span data-stu-id="70865-109">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="70865-110">"SetAttributeValue" und "SetElementValue"</span><span class="sxs-lookup"><span data-stu-id="70865-110">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="70865-111">Zum Unterhalten von Name/Wert-Paaren stehen die folgenden beiden Methoden zur Verfügung: <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> und <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="70865-111">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="70865-112">Diese beiden Methoden besitzen eine ähnliche Semantik.</span><span class="sxs-lookup"><span data-stu-id="70865-112">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="70865-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> kann Attribute eines Elements hinzufügen, Attribute ändern oder Attribute entfernen.</span><span class="sxs-lookup"><span data-stu-id="70865-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="70865-114">Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines Attributs aufrufen, das nicht existiert, erstellt die Methode ein neues Attribut und fügt dieses dem angegebenen Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="70865-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="70865-115">Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines vorhandenen Attributs und einem angegebenen Inhalt aufrufen, wird der Inhalt des Attributs durch den angegebenen Inhalt ersetzt.</span><span class="sxs-lookup"><span data-stu-id="70865-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="70865-116">Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines vorhandenen Attributs aufrufen und für den Inhalt einen NULL-Wert angeben, wird das Attribut aus dem übergeordneten Element entfernt.</span><span class="sxs-lookup"><span data-stu-id="70865-116">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="70865-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> kann untergeordnete Elemente eines Elements hinzufügen, ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="70865-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="70865-118">Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines untergeordneten Elements aufrufen, das nicht existiert, erstellt die Methode ein neues Element und fügt dieses dem angegebenen Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="70865-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="70865-119">Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines vorhandenen Elements und einem angegebenen Inhalt aufrufen, wird der Inhalt des Elements durch den angegebenen Inhalt ersetzt.</span><span class="sxs-lookup"><span data-stu-id="70865-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="70865-120">Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines vorhandenen Elements aufrufen und für den Inhalt einen NULL-Wert angeben, wird das Element aus dem übergeordneten Element entfernt.</span><span class="sxs-lookup"><span data-stu-id="70865-120">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70865-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70865-121">Example</span></span>  
 <span data-ttu-id="70865-122">Das folgende Beispiel erstellt ein Element, das keine Attribute besitzt.</span><span class="sxs-lookup"><span data-stu-id="70865-122">The following example creates an element with no attributes.</span></span> <span data-ttu-id="70865-123">Es verwendet dann die <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>-Methode, um eine Liste von Name/Wert-Paaren zu erstellen und zu unterhalten.</span><span class="sxs-lookup"><span data-stu-id="70865-123">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="70865-124">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="70865-124">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="70865-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70865-125">Example</span></span>  
 <span data-ttu-id="70865-126">Das folgende Beispiel erstellt ein Element, das keine untergeordneten Elemente besitzt.</span><span class="sxs-lookup"><span data-stu-id="70865-126">The following example creates an element with no child elements.</span></span> <span data-ttu-id="70865-127">Es verwendet dann die <xref:System.Xml.Linq.XElement.SetElementValue%2A>-Methode, um eine Liste von Name/Wert-Paaren zu erstellen und zu unterhalten.</span><span class="sxs-lookup"><span data-stu-id="70865-127">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="70865-128">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="70865-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70865-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70865-129">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="70865-130">Modifying XML Trees (LINQ to XML) (C#) (Ändern von XML-Strukturen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="70865-130">Modifying XML Trees (LINQ to XML) (C#)</span></span>](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)
