---
title: Ändern von Elementen, Attributen und Knoten in einer XML-Struktur
description: Erfahren Sie mehr über die Methoden und Eigenschaften, die Sie zum Ändern eines Elements sowie der untergeordneten Knoten oder der Attribute des Elements verwenden können.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: bfff882dc57a4f6f4b228563ac923122097d88d0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303165"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="0c4c5-103">Ändern von Elementen, Attributen und Knoten in einer XML-Struktur</span><span class="sxs-lookup"><span data-stu-id="0c4c5-103">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="0c4c5-104">Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="0c4c5-105">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XElement>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-105">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="0c4c5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="0c4c5-106">Method</span></span>|<span data-ttu-id="0c4c5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c4c5-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-108">Ersetzt ein Element durch analysiertes XML.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-108">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-109">Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-109">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-110">Entfernt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-110">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-111">Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-111">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-112">Ersetzt die Attribute eines Elements.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-112">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-113">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-113">Sets the value of an attribute.</span></span> <span data-ttu-id="0c4c5-114">Erstellt das Attribut, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="0c4c5-115">Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-115">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-116">Legt den Wert eines untergeordneten Elements fest.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-116">Sets the value of a child element.</span></span> <span data-ttu-id="0c4c5-117">Erstellt das Element, wenn es nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="0c4c5-118">Entfernt das Element, wenn der Wert auf `null` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-118">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-119">Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-120">Legt den Wert eines Elements fest.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-120">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="0c4c5-121">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XAttribute>-Objekt geändert.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="0c4c5-122">Methode</span><span class="sxs-lookup"><span data-stu-id="0c4c5-122">Method</span></span>|<span data-ttu-id="0c4c5-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c4c5-123">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-124">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-124">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-125">Legt den Wert eines Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-125">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="0c4c5-126">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XNode> (einschließlich <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="0c4c5-127">Methode</span><span class="sxs-lookup"><span data-stu-id="0c4c5-127">Method</span></span>|<span data-ttu-id="0c4c5-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c4c5-128">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-129">Ersetzt einen Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-129">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="0c4c5-130">Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="0c4c5-131">Methode</span><span class="sxs-lookup"><span data-stu-id="0c4c5-131">Method</span></span>|<span data-ttu-id="0c4c5-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c4c5-132">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="0c4c5-133">Ersetzt die untergeordneten Knoten durch neuen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0c4c5-133">Replaces the children nodes with new content.</span></span>|  
