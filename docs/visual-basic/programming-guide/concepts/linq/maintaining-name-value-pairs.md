---
title: Warten von Name-Wert-Paaren (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 30e40c73430f385815b7a08a2507343db0fafd4f
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="71295-102">Verwalten von Name/Wert-Paaren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71295-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="71295-103">Viele Anwendungen müssen Informationen verwalten, die am besten als Name/Wert-Paare geführt werden.</span><span class="sxs-lookup"><span data-stu-id="71295-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="71295-104">Solche Informationen können z. B. Konfigurationsinformationen oder globale Einstellungen sein.</span><span class="sxs-lookup"><span data-stu-id="71295-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="71295-105"> enthält einige Methoden, die das Unterhalten von Name/Wert-Paaren vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="71295-105"> contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="71295-106">Sie können die Informationen entweder als Attribute oder als Satz untergeordneter Elemente unterhalten.</span><span class="sxs-lookup"><span data-stu-id="71295-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="71295-107">Ein Unterschied zwischen diesen beiden Formen besteht darin, dass Attribute der Beschränkung unterliegen, dass pro Element immer nur ein Attribut mit einem bestimmten Namen vorhanden sein darf.</span><span class="sxs-lookup"><span data-stu-id="71295-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="71295-108">Für untergeordnete Elemente gilt diese Einschränkung nicht.</span><span class="sxs-lookup"><span data-stu-id="71295-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="71295-109">"SetAttributeValue" und "SetElementValue"</span><span class="sxs-lookup"><span data-stu-id="71295-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="71295-110">Die zwei Methoden, vereinfachen Name/Wert-Paare sind <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>und <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="71295-111">Diese beiden Methoden besitzen eine ähnliche Semantik.</span><span class="sxs-lookup"><span data-stu-id="71295-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="71295-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A>können hinzufügen, ändern oder Entfernen von Attributen eines Elements.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
-   <span data-ttu-id="71295-113">Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>mit einem Namen eines Attributs, das nicht vorhanden ist, die Methode erstellt ein neues Attribut und fügt es in das angegebene Element hinzu.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="71295-114">Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>mit einem Namen eines vorhandenen Attributs und einem angegebenen Inhalt aus, der Inhalt des Attributs ersetzt durch den angegebenen Inhalt.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="71295-115">Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>mit einem Namen eines vorhandenen Attribut, und geben Sie null für den Inhalt das Attribut aus dem übergeordneten Element entfernt.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="71295-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A>können hinzufügen, ändern oder entfernen die untergeordneten Elemente eines Elements.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
-   <span data-ttu-id="71295-117">Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetElementValue%2A>mit einem Namen eines untergeordneten Elements, das nicht vorhanden ist, die Methode erstellt ein neues Element und fügt es in das angegebene Element hinzu.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="71295-118">Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetElementValue%2A>mit einem Namen eines vorhandenen Elements und einem angegebenen Inhalt, den Inhalt des Elements ersetzt durch den angegebenen Inhalt.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="71295-119">Wenn Sie aufrufen <xref:System.Xml.Linq.XElement.SetElementValue%2A>mit einem Namen eines vorhandenen Elements, und geben Sie null für den Inhalt, wird das Element aus dem übergeordneten Element entfernt.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71295-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71295-120">Example</span></span>  
 <span data-ttu-id="71295-121">Das folgende Beispiel erstellt ein Element, das keine Attribute besitzt.</span><span class="sxs-lookup"><span data-stu-id="71295-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="71295-122">Anschließend wird mithilfe der <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>-Methode zum Erstellen und verwalten Sie eine Liste von Name/Wert-Paaren.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
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
  
 <span data-ttu-id="71295-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="71295-123">This example produces the following output:</span></span>  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="71295-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71295-124">Example</span></span>  
 <span data-ttu-id="71295-125">Das folgende Beispiel erstellt ein Element, das keine untergeordneten Elemente besitzt.</span><span class="sxs-lookup"><span data-stu-id="71295-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="71295-126">Anschließend wird mithilfe der <xref:System.Xml.Linq.XElement.SetElementValue%2A>-Methode zum Erstellen und verwalten Sie eine Liste von Name/Wert-Paaren.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
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
  
 <span data-ttu-id="71295-127">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="71295-127">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="71295-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71295-128">See Also</span></span>  
 <span data-ttu-id="71295-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span></span>   
 <span data-ttu-id="71295-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="71295-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></span></span>   
<span data-ttu-id="71295-131"> [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="71295-131"> [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span></span>
