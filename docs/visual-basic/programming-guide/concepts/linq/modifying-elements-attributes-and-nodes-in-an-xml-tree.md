---
title: "Ändern von Elementen, Attributen und Knoten in ein XML-Tree1 | Microsoft-Dokumentation"
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
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88531f2af88074f4406c4859354860829efda69f
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="84da6-102">Ändern von Elementen, Attributen und Knoten in einer XML-Struktur</span><span class="sxs-lookup"><span data-stu-id="84da6-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="84da6-103">Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.</span><span class="sxs-lookup"><span data-stu-id="84da6-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="84da6-104">Ändern Sie die folgenden Methoden eine <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="84da6-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="84da6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="84da6-105">Method</span></span>|<span data-ttu-id="84da6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84da6-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="84da6-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-108">Ersetzt ein Element durch analysiertes XML.</span><span class="sxs-lookup"><span data-stu-id="84da6-108">Replaces an element with parsed XML.</span></span>|  
|<span data-ttu-id="84da6-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-110">Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="84da6-110">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="84da6-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-112">Entfernt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="84da6-112">Removes the attributes of an element.</span></span>|  
|<span data-ttu-id="84da6-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-114">Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="84da6-114">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="84da6-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-116">Ersetzt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="84da6-116">Replaces the attributes of an element.</span></span>|  
|<span data-ttu-id="84da6-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-118">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="84da6-118">Sets the value of an attribute.</span></span> <span data-ttu-id="84da6-119">Erstellt das Attribut, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="84da6-119">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="84da6-120">Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="84da6-120">If the value is set to `null`, removes the attribute.</span></span>|  
|<span data-ttu-id="84da6-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-122">Legt den Wert eines untergeordneten Elements fest.</span><span class="sxs-lookup"><span data-stu-id="84da6-122">Sets the value of a child element.</span></span> <span data-ttu-id="84da6-123">Erstellt das Element, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="84da6-123">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="84da6-124">Entfernt das Element, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="84da6-124">If the value is set to `null`, removes the element.</span></span>|  
|<span data-ttu-id="84da6-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-126">Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="84da6-126">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<span data-ttu-id="84da6-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-128">Legt den Wert eines Elements fest.</span><span class="sxs-lookup"><span data-stu-id="84da6-128">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="84da6-129">Ändern Sie die folgenden Methoden eine <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="84da6-129">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="84da6-130">Methode</span><span class="sxs-lookup"><span data-stu-id="84da6-130">Method</span></span>|<span data-ttu-id="84da6-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84da6-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="84da6-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-133">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="84da6-133">Sets the value of an attribute.</span></span>|  
|<span data-ttu-id="84da6-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-135">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="84da6-135">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="84da6-136">Ändern Sie die folgenden Methoden eine <xref:System.Xml.Linq.XNode>(z. B. ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="84da6-136">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="84da6-137">Methode</span><span class="sxs-lookup"><span data-stu-id="84da6-137">Method</span></span>|<span data-ttu-id="84da6-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84da6-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="84da6-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-140">Ersetzt einen Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="84da6-140">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="84da6-141">Ändern Sie die folgenden Methoden eine <xref:System.Xml.Linq.XContainer>(eine <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="84da6-141">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="84da6-142">Methode</span><span class="sxs-lookup"><span data-stu-id="84da6-142">Method</span></span>|<span data-ttu-id="84da6-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84da6-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="84da6-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84da6-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="84da6-145">Ersetzt die untergeordneten Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="84da6-145">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84da6-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84da6-146">See Also</span></span>  
 [<span data-ttu-id="84da6-147">Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84da6-147">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
