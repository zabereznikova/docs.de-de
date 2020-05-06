---
title: Warten von Name-Wert-Paaren
ms.date: 07/20/2015
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
ms.openlocfilehash: b8c9487330239e7e6365055d5f08a02f2dbb0e37
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796144"
---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="d493b-102">Warten von Name-Wert-Paaren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d493b-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="d493b-103">Viele Anwendungen müssen Informationen verwalten, die am besten als Name/Wert-Paare geführt werden.</span><span class="sxs-lookup"><span data-stu-id="d493b-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="d493b-104">Solche Informationen können z. B. Konfigurationsinformationen oder globale Einstellungen sein.</span><span class="sxs-lookup"><span data-stu-id="d493b-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="d493b-105">enthält einige Methoden, die das Unterhalten von Name/Wert-Paaren vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d493b-105">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="d493b-106">Sie können die Informationen entweder als Attribute oder als Satz untergeordneter Elemente unterhalten.</span><span class="sxs-lookup"><span data-stu-id="d493b-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="d493b-107">Ein Unterschied zwischen diesen beiden Formen besteht darin, dass Attribute der Beschränkung unterliegen, dass pro Element immer nur ein Attribut mit einem bestimmten Namen vorhanden sein darf.</span><span class="sxs-lookup"><span data-stu-id="d493b-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="d493b-108">Für untergeordnete Elemente gilt diese Einschränkung nicht.</span><span class="sxs-lookup"><span data-stu-id="d493b-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="d493b-109">"SetAttributeValue" und "SetElementValue"</span><span class="sxs-lookup"><span data-stu-id="d493b-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="d493b-110">Zum Unterhalten von Name/Wert-Paaren stehen die folgenden beiden Methoden zur Verfügung: <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> und <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="d493b-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="d493b-111">Diese beiden Methoden besitzen eine ähnliche Semantik.</span><span class="sxs-lookup"><span data-stu-id="d493b-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="d493b-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> kann Attribute eines Elements hinzufügen, Attribute ändern oder Attribute entfernen.</span><span class="sxs-lookup"><span data-stu-id="d493b-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="d493b-113">Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines Attributs aufrufen, das nicht existiert, erstellt die Methode ein neues Attribut und fügt dieses dem angegebenen Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d493b-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="d493b-114">Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines vorhandenen Attributs und einem angegebenen Inhalt aufrufen, wird der Inhalt des Attributs durch den angegebenen Inhalt ersetzt.</span><span class="sxs-lookup"><span data-stu-id="d493b-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="d493b-115">Wenn Sie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> mit einem Namen eines vorhandenen Attributs aufrufen und für den Inhalt einen NULL-Wert angeben, wird das Attribut aus dem übergeordneten Element entfernt.</span><span class="sxs-lookup"><span data-stu-id="d493b-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="d493b-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> kann untergeordnete Elemente eines Elements hinzufügen, ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="d493b-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="d493b-117">Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines untergeordneten Elements aufrufen, das nicht existiert, erstellt die Methode ein neues Element und fügt dieses dem angegebenen Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d493b-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="d493b-118">Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines vorhandenen Elements und einem angegebenen Inhalt aufrufen, wird der Inhalt des Elements durch den angegebenen Inhalt ersetzt.</span><span class="sxs-lookup"><span data-stu-id="d493b-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="d493b-119">Wenn Sie <xref:System.Xml.Linq.XElement.SetElementValue%2A> mit einem Namen eines vorhandenen Elements aufrufen und für den Inhalt einen NULL-Wert angeben, wird das Element aus dem übergeordneten Element entfernt.</span><span class="sxs-lookup"><span data-stu-id="d493b-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d493b-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d493b-120">Example</span></span>  
 <span data-ttu-id="d493b-121">Das folgende Beispiel erstellt ein Element, das keine Attribute besitzt.</span><span class="sxs-lookup"><span data-stu-id="d493b-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="d493b-122">Es verwendet dann die <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>-Methode, um eine Liste von Name/Wert-Paaren zu erstellen und zu unterhalten.</span><span class="sxs-lookup"><span data-stu-id="d493b-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="d493b-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d493b-123">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="d493b-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d493b-124">Example</span></span>  
 <span data-ttu-id="d493b-125">Das folgende Beispiel erstellt ein Element, das keine untergeordneten Elemente besitzt.</span><span class="sxs-lookup"><span data-stu-id="d493b-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="d493b-126">Es verwendet dann die <xref:System.Xml.Linq.XElement.SetElementValue%2A>-Methode, um eine Liste von Name/Wert-Paaren zu erstellen und zu unterhalten.</span><span class="sxs-lookup"><span data-stu-id="d493b-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="d493b-127">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d493b-127">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d493b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d493b-128">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="d493b-129">Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d493b-129">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
