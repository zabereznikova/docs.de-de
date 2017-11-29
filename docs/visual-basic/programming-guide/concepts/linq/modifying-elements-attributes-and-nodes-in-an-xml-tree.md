---
title: "Ändern von Elementen, Attributen und Knoten in ein XML-Tree1"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c769885d958abeaa92e19ef0b20d695fbcc4b96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="ad37c-102">Ändern von Elementen, Attributen und Knoten in einer XML-Struktur</span><span class="sxs-lookup"><span data-stu-id="ad37c-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="ad37c-103">Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ad37c-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="ad37c-104">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XElement>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="ad37c-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="ad37c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ad37c-105">Method</span></span>|<span data-ttu-id="ad37c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad37c-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-107">Ersetzt ein Element durch analysiertes XML.</span><span class="sxs-lookup"><span data-stu-id="ad37c-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-108">Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="ad37c-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-109">Entfernt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="ad37c-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-110">Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="ad37c-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-111">Ersetzt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="ad37c-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-112">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="ad37c-112">Sets the value of an attribute.</span></span> <span data-ttu-id="ad37c-113">Erstellt das Attribut, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="ad37c-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="ad37c-114">Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="ad37c-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-115">Legt den Wert eines untergeordneten Elements fest.</span><span class="sxs-lookup"><span data-stu-id="ad37c-115">Sets the value of a child element.</span></span> <span data-ttu-id="ad37c-116">Erstellt das Element, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="ad37c-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="ad37c-117">Entfernt das Element, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="ad37c-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-118">Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="ad37c-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-119">Legt den Wert eines Elements fest.</span><span class="sxs-lookup"><span data-stu-id="ad37c-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="ad37c-120">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XAttribute>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="ad37c-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="ad37c-121">Methode</span><span class="sxs-lookup"><span data-stu-id="ad37c-121">Method</span></span>|<span data-ttu-id="ad37c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad37c-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-123">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="ad37c-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-124">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="ad37c-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="ad37c-125">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XNode> (einschließlich <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="ad37c-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="ad37c-126">Methode</span><span class="sxs-lookup"><span data-stu-id="ad37c-126">Method</span></span>|<span data-ttu-id="ad37c-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad37c-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-128">Ersetzt einen Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="ad37c-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="ad37c-129">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="ad37c-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="ad37c-130">Methode</span><span class="sxs-lookup"><span data-stu-id="ad37c-130">Method</span></span>|<span data-ttu-id="ad37c-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad37c-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="ad37c-132">Ersetzt die untergeordneten Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="ad37c-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad37c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad37c-133">See Also</span></span>  
 [<span data-ttu-id="ad37c-134">Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad37c-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
