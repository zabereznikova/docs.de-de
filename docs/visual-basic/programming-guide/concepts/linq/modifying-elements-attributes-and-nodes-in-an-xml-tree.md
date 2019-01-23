---
title: Ändern von Elementen, Attributen und Knoten in einem XML-Tree1
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: c3863f52976303407cbad3d0bacc9bd0b2ec1d31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547539"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="981e5-102">Ändern von Elementen, Attributen und Knoten in einer XML-Struktur</span><span class="sxs-lookup"><span data-stu-id="981e5-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="981e5-103">Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.</span><span class="sxs-lookup"><span data-stu-id="981e5-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="981e5-104">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XElement>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="981e5-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="981e5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="981e5-105">Method</span></span>|<span data-ttu-id="981e5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="981e5-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-107">Ersetzt ein Element durch analysiertes XML.</span><span class="sxs-lookup"><span data-stu-id="981e5-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-108">Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="981e5-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-109">Entfernt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="981e5-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-110">Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="981e5-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-111">Ersetzt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="981e5-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-112">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="981e5-112">Sets the value of an attribute.</span></span> <span data-ttu-id="981e5-113">Erstellt das Attribut, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="981e5-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="981e5-114">Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="981e5-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-115">Legt den Wert eines untergeordneten Elements fest.</span><span class="sxs-lookup"><span data-stu-id="981e5-115">Sets the value of a child element.</span></span> <span data-ttu-id="981e5-116">Erstellt das Element, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="981e5-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="981e5-117">Entfernt das Element, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="981e5-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-118">Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="981e5-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-119">Legt den Wert eines Elements fest.</span><span class="sxs-lookup"><span data-stu-id="981e5-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="981e5-120">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XAttribute>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="981e5-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="981e5-121">Methode</span><span class="sxs-lookup"><span data-stu-id="981e5-121">Method</span></span>|<span data-ttu-id="981e5-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="981e5-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-123">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="981e5-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-124">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="981e5-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="981e5-125">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XNode> (einschließlich <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="981e5-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="981e5-126">Methode</span><span class="sxs-lookup"><span data-stu-id="981e5-126">Method</span></span>|<span data-ttu-id="981e5-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="981e5-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-128">Ersetzt einen Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="981e5-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="981e5-129">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="981e5-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="981e5-130">Methode</span><span class="sxs-lookup"><span data-stu-id="981e5-130">Method</span></span>|<span data-ttu-id="981e5-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="981e5-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="981e5-132">Ersetzt die untergeordneten Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="981e5-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="981e5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="981e5-133">See also</span></span>
- [<span data-ttu-id="981e5-134">Ändern von XML-Bäumen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="981e5-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
