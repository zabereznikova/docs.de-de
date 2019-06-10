---
title: Ändern von Elementen, Attributen und Knoten in einem XML-Struktur
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 93a4d67129e22d0bbeef464c1d4d8758439edb7b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484236"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="541c0-102">Ändern von Elementen, Attributen und Knoten in einer XML-Struktur</span><span class="sxs-lookup"><span data-stu-id="541c0-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="541c0-103">Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.</span><span class="sxs-lookup"><span data-stu-id="541c0-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="541c0-104">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XElement>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="541c0-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="541c0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="541c0-105">Method</span></span>|<span data-ttu-id="541c0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="541c0-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-107">Ersetzt ein Element durch analysiertes XML.</span><span class="sxs-lookup"><span data-stu-id="541c0-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-108">Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="541c0-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-109">Entfernt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="541c0-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-110">Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="541c0-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-111">Ersetzt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="541c0-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-112">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="541c0-112">Sets the value of an attribute.</span></span> <span data-ttu-id="541c0-113">Erstellt das Attribut, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="541c0-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="541c0-114">Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="541c0-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-115">Legt den Wert eines untergeordneten Elements fest.</span><span class="sxs-lookup"><span data-stu-id="541c0-115">Sets the value of a child element.</span></span> <span data-ttu-id="541c0-116">Erstellt das Element, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="541c0-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="541c0-117">Entfernt das Element, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="541c0-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-118">Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="541c0-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-119">Legt den Wert eines Elements fest.</span><span class="sxs-lookup"><span data-stu-id="541c0-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="541c0-120">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XAttribute>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="541c0-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="541c0-121">Methode</span><span class="sxs-lookup"><span data-stu-id="541c0-121">Method</span></span>|<span data-ttu-id="541c0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="541c0-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-123">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="541c0-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-124">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="541c0-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="541c0-125">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XNode> (einschließlich <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="541c0-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="541c0-126">Methode</span><span class="sxs-lookup"><span data-stu-id="541c0-126">Method</span></span>|<span data-ttu-id="541c0-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="541c0-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-128">Ersetzt einen Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="541c0-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="541c0-129">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="541c0-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="541c0-130">Methode</span><span class="sxs-lookup"><span data-stu-id="541c0-130">Method</span></span>|<span data-ttu-id="541c0-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="541c0-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="541c0-132">Ersetzt die untergeordneten Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="541c0-132">Replaces the children nodes with new content.</span></span>|  
